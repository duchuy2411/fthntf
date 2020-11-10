<template>
  <div class="d_select-comp">
    <fieldset>
      <legend>{{title}}</legend>
      <select name="" id="">
        <option value="" selected></option>
        <option value="" v-for="(item,index) in itemList" v-bind:key="index">{{item.value}}</option>
      </select>
    </fieldset>
  </div>
</template>

<script>
export default {
  name: "select-comp",
  props: {
    title: String,
    itemList:{
      type: Array,
    },
  },
  data() {
    return {
      
    };
  },
  methods: {},
  components: {},
};
</script>

<style >

.d_select-comp>fieldset{
  border-radius:5px;
  border: 1px solid rgb(194, 187, 187);
}

.d_select-comp>fieldset>select{
  border: none;
  width: 100%;
  background-color:#ffffff;
}

.d_select-comp>fieldset>legend{
   font-size: 0.875rem;
}

.d_select-comp>select>option:first-child{
  display: none;
}

.d_select-comp>fieldset>select {
  -webkit-appearance: none;
  -moz-appearance: none;
  background: transparent;
  background-image: url("data:image/svg+xml;utf8,<svg fill='black' height='24' viewBox='0 0 24 24' width='24' xmlns='http://www.w3.org/2000/svg'><path d='M7 10l5 5 5-5z'/><path d='M0 0h24v24H0z' fill='none'/></svg>");
  background-repeat: no-repeat;
  background-position-x: 100%;
  background-position-y: 50%;
}

</style>