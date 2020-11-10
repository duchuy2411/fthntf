<template>
    <div class="d_input-text">
        <fieldset v-bind:class="{'d_focus-in':isFocusIn}"
            v-on:focusin="handleFocusIn()"
            v-on:focusout="handleFocusOut()">
        <legend><p>{{title}}</p></legend>
        <input v-bind:type="inputType" name="teamSize" id="teamSize" v-bind:readonly="isReadOnly">
      </fieldset>
    </div>
</template>

<script>
export default {
    name:'input-text-comp', 
    props:{
        title:String,
        isReadOnly:{
            type:Boolean,
            default:false,
        },
        inputType:{
            type:String, 
            default:`text`
        }
    }, 
    data(){
        return{
            isFocusIn:false,
        }
    }, 
    methods:{
        handleFocusIn:function(){
            this.isFocusIn=true;
        }, 
        handleFocusOut:function(){
            this.isFocusIn=false;
        }
    }
}
</script>

<style scoped>
fieldset {
  border-radius: 5px;
  text-align: left;
  border: 1px solid rgb(194, 187, 187);
  margin-bottom:1rem;
}

.d_input-text > fieldset > input {
    width:100%;
    border:none;
}


.d_input-text > fieldset > legend > p{
  margin: 0 0.5rem;
  font-size: 0.875rem;
}

.d_input-text > fieldset > input:focus{
    border: none;
    outline: none;
}

.d_focus-in{
    border:1px solid purple;
}
</style>