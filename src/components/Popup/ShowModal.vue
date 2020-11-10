<template>
<div @click="hideModal" class="d_modal" id="d_modal">
    <SwitchModal :data="data" class="d_modal-content" :switchmodal="modalName" />
</div>
</template>

<script>
import SwitchModal from '@/components/Popup/SwitchModal.vue';

export default {
    name: 'show-modal',

    props: {
        modalName: {
            type: String,
            defaults: 'Project'
        },
        data: {
            type: Object
        }
    },
    data() {
        return {
        }
    },
    methods: {
        hideModal: function (e) {
            if (e.target === document.getElementById("d_modal")) {
                this.$emit('hide-modal');
            }
        }
    },
    components: {
        SwitchModal
    },

}
</script>

<style>
.d_modal {
    /*display: none;*/
    position: absolute;
    z-index: 1;
    padding-top: 100px;
    /* Location of the box */
    top: 0;
    left: 0;
    width: 100%;
    /* Full width */
    height: 100%;
    /* Full height */
    overflow: auto;
    /* Enable scroll if needed */
    background-color: rgb(0, 0, 0);
    /* Fallback color */
    background-color: rgba(0, 0, 0, 0.4);
    /* Black w/ opacity */
}

.d_modal-content {
    background-color: #fefefe;
    margin: auto;
    border: 1px solid #888;
}
</style>
