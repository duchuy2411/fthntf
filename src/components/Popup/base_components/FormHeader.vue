<template>
  <div class="d_header">
    <p>{{ title }}</p>
  </div>
</template>

<script>
export default {
  name: "form-header",
  props: {
    title: String
  },
  data() {
    return {};
  },
};
</script>

<style scoped>
.d_header {
  display: inline-block;
  margin: auto;
  width: 50%;
}

.d_header>p {
  margin: 1rem;
  font-size: 1.125rem;
  font-weight: bold;
}
</style>