<template>
<div class="d_input-date-picker">
    <input-text-comp v-bind:title="`To`" v-bind:isReadOnly="isReadOnly"></input-text-comp>
    <input-text-comp v-bind:title="`From`" v-bind:isReadOnly="isReadOnly"></input-text-comp>
</div>    
</template>

<script>
import InputTextComp from './InputTextComp.vue';

export default{
    name:'input-date-picker-comp',
    data(){
        return {
             isReadOnly:true,
        }
    }, 
    components:{
        InputTextComp, 

    }
}
</script>

<style scoped>
.d_input-date-picker {
  display: flex;
  justify-content: space-between;
}

.d_input-date-picker > *{
    width:49%;
}
</style>