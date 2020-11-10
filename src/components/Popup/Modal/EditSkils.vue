<template>
<div class="d_form-body">
    <form action="">
        <input-text-comp 
                    v-bind:title="`Title`" 
                    :value="data.title" ></input-text-comp>
        <!-- base-components: delete, add 1 tag pill -->
        <input-skills-comp 
                    @delete-skill="deleteSkill" 
                    @add-skill="addSkill" 
                    :skills="data.skills" 
                    v-bind:title="`Skills`"></input-skills-comp>

        <div class="d_list-btn">
            <button-comp class="d_cacel-btn" v-bind:value="`CANCEL`" v-bind:type="`button`"></button-comp>
            <button-comp class="d_delete-btn" v-bind:value="`DELETE`" v-bind:type="`button`"></button-comp>
            <button-comp class="d_save-btn" v-bind:value="`SAVE`" v-bind:type="`submit`"></button-comp>
        </div>
    </form>
</div>
</template>

<script>
//  regex : ([A-Za-z1-9]{1,20}[^\,]{1}){1,20}

import InputTextComp from "@/components/Popup/base_components/InputTextComp.vue";
import InputDatePickerComp from "@/components/Popup/base_components/InputDatePickerComp.vue";
import ButtonComp from "@/components/Popup/base_components/ButtonComp.vue";
import SelectComp from "@/components/Popup/base_components/SelectComp.vue";
import InputSkillsComp from "@/components/Popup/base_components/InputSkillsComp.vue";

export default {
    props: {
        data: Object
    },
    data() {
        return {
            skills: ["Python", "Java"]
        }
    },
    methods: {
        
        handleFocusIn: function () {
            this.isFocusIn = true;
            console.log(event);
        },

        handleFocusOut: function () {
            this.isFocusIn = false;
        },

        addSkill: function (skill) {
            this.skills.push(skill);
        },

        deleteSkill: function (skill) {
            this.skills.splice(this.skills.indexOf(skill), 1);
        }

    },
    components: {
        InputTextComp,
        InputSkillsComp,
        InputDatePickerComp,
        ButtonComp,
        SelectComp,
    },
}
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

.d_select-comp-mb {
    margin-bottom: 1rem;
}
</style>
