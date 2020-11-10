<template>
  <div class="d_project-popup d_modal-content">
    <form-header :title="switchmodal"></form-header>
    <hr />

    <edit-project       v-if="switchmodal === `Project`">       </edit-project>
    <edit-skills        v-if="switchmodal === `Skills`">        </edit-skills>
    <edit-certificates  v-if="switchmodal === `Certificates`">  </edit-certificates>
    <edit-education     v-if="switchmodal === `Education`">     </edit-education>
    <edit-professional  v-if="switchmodal === `Professional`">  </edit-professional>

  </div>
</template>

<script>

import FormHeader from "@/components/Popup/base_components/FormHeader.vue";
import EditProject from "@/components/Popup/Modal/EditProject.vue";
import EditSkills from "@/components/Popup/Modal/EditSkils.vue"
import EditCertificates from "@/components/Popup/Modal/EditCertificates.vue"
import EditEducation from "@/components/Popup/Modal/EditEducation.vue"
import EditProfessional from "@/components/Popup/Modal/EditProfessional.vue"

export default {
  name: "modal",
  props: {
    switchmodal: String
  },
  data() {
    return {};
  },
  components: {
    FormHeader,
    EditProject,
    EditSkills,
    EditCertificates,
    EditEducation,
    EditProfessional
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