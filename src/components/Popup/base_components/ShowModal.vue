<template>
    <div @click="hideModal" class="d_modal" id="d_modal">
          {{ modalName }}
         <ProjectModal class="d_modal-content" v-if="modalName==='project'"></ProjectModal>
    </div>
</template>

<script>
import ProjectModal from './ProjectModal.vue';

export default{
    name:'show-modal', 
    props:{
        modalName:{
          type:String, 
          default: ''
        }
    }, 
    data(){
        return {

        }
    }, 
    methods:{
      hideModal : function () {
        this.$emit('hide-modal');
      }
    }, 
    components:{
        ProjectModal,
    }, 

    mounted() {
      console.log()
    },
}
</script>

<style>
.d_modal {
  /*display: none;*/
  position: absolute;
  z-index: 1;
  padding-top: 100px; /* Location of the box */
  top: 0;
  left: 0;
  width: 100%; /* Full width */
  height: 100%; /* Full height */
  overflow: auto; /* Enable scroll if needed */
  background-color: rgb(0, 0, 0); /* Fallback color */
  background-color: rgba(0, 0, 0, 0.4); /* Black w/ opacity */
}

.d_modal-content {
  background-color: #fefefe;
  margin: auto;
  border: 1px solid #888;
}
</style>