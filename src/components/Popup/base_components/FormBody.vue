<template>
  <div class="d_form-body">
    <form action="">
      <input-text-comp v-bind:title="`Name`"></input-text-comp>
      <input-date-picker-comp></input-date-picker-comp>
      <select-comp
        class="d_select-comp-mb"
        v-bind:title="`Position`"
        v-bind:itemList="positionList"
      ></select-comp>
      <input-text-comp v-bind:title="`Description`"></input-text-comp>
      <input-text-comp v-bind:title="`Responsibilities`"></input-text-comp>
      <select-comp
        class="d_select-comp-mb"
        v-bind:title="`Team size`"
        v-bind:itemList="teamSizeList"
      ></select-comp>
      <input-text-comp v-bind:title="`Technologies`"></input-text-comp>
      <div class="d_list-btn">
        <button-comp
          class="d_cacel-btn"
          v-bind:value="`CANCEL`"
          v-bind:type="`button`"
        ></button-comp>
        <button-comp
          class="d_delete-btn"
          v-bind:value="`DELETE`"
          v-bind:type="`button`"
        ></button-comp>
        <button-comp
          class="d_save-btn"
          v-bind:value="`SAVE`"
          v-bind:type="`submit`"
        ></button-comp>
      </div>
    </form>
  </div>
</template>

<script>
import InputTextComp from "./InputTextComp.vue";
import InputDatePickerComp from "./InputDatePickerComp.vue";
import ButtonComp from "./ButtonComp.vue";
import SelectComp from "./SelectComp.vue";

export default {
  name: "form-body",
  data() {
    return {
      isFocusIn: false,
      positionList: [
        { id: 1, value: "Team Leader" },
        { id: 2, value: "Project Manager" },
        { id: 3, value: "Developer" },
        { id: 4, value: "Tester" },
      ],
      teamSizeList: [
        { id: 1, value:1},
        { id: 2, value:2},
        { id: 3, value:3},
        { id: 4, value:4},
      ],
    };
  },
  methods: {
    handleFocusIn: function () {
      this.isFocusIn = true;
      console.log(event);
    },

    handleFocusOut: function () {
      this.isFocusIn = false;
    },
  },
  components: {
    InputTextComp,
    InputDatePickerComp,
    ButtonComp,
    SelectComp,
  },
};
</script>

<style scoped>
.d_form-body {
  margin: 1rem;
  overflow: auto;
}

.d_active-focusin {
  border: 1px solid rebeccapurple;
}

.d_list-btn {
  float: right;
  clear: both;
}

.d_delete-btn {
  background-color: #f44336;
  color: #ffffff;
}

.d_save-btn {
  background-color: #1867c0;
  color: #ffffff;
}

.d_select-comp-mb{
  margin-bottom: 1rem;
}
</style>