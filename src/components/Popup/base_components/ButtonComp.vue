<template>
  <input class="d_btn-comp" v-bind:type="type" v-bind:value="value" />
</template>

<script>
export default {
  name: "button-comp",
  props: {
    value: {
      type: String,
    },
    type: {
      type: String,
      default: `text`,
    },
  },
  data() {
    return {};
  },
};
</script>

<style scoped>

.d_btn-comp{
    margin: 0.2rem;
    width: 7.5rem;
    height: 2.5rem;
    font-size: 0.875rem;
    border: 1px solid rgb(199, 193, 193);
    border-radius: 5px;
}
</style>