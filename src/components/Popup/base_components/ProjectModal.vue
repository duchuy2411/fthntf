<template>
  <div class="d_project-popup d_modal-content">
    <form-header></form-header>
    <hr />
    <form-body></form-body>
  </div>
</template>

<script>
import FormHeader from "./FormHeader.vue";
import FormBody from "./FormBody.vue";

export default {
  name: "project-modal",
  data() {
    return {};
  },
  components: {
    FormHeader,
    FormBody,
  },
};
</script>

<style>
.d_project-popup {
  border: 1px solid #e5e5e5;
  box-sizing: border-box;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  background-color: #ffffff;
  width: 40%;
}

@media only screen and (max-width: 1000px) {
  .d_project-popup {
    width: 80%;
  }
}

@media only screen and (max-width: 500px) {
  .d_project-popup{
    width:90%;
  }
}

hr {
  color: rgba(250, 240, 240, 0.781);
  margin: 0;
}

</style>