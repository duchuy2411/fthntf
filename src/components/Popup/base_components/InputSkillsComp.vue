<template>
<form @submit="handleSubmit">
    <div class="d_input-text">

        <fieldset v-bind:class="{'d_focus-in':isFocusIn}" v-on:focusin="handleFocusIn()" v-on:focusout="handleFocusOut()" @click="handleClick()">

            <legend>
                <p>{{title}}</p>
            </legend>

            <span :key="tag" v-for="tag in arraySkill" class="tag-pill">{{ tag }}
                <!-- icon x delete 1 tag -->
                <i @click="deleteTag(tag)"><img src="@/assets/cancel.png" width="10px" height="10px"></i>
            </span>

            <input v-model="skillInput" name="skill" id="skill" v-if="showInputSkill">
            <button type="submit"></button>
        </fieldset>

    </div>
</form>
</template>

<script>
export default {
    name: 'input-skills-comp',
    props: {
        title: String,

        skills: {
            type: Array
        }
    },
    data() {
        return {
            skillInput: "",
            isFocusIn: false,
            showInputSkill: false,
            arraySkill: this.skills
        }
    },
    methods: {
        handleFocusIn: function () {
            this.isFocusIn = true;
        },
        handleFocusOut: function () {
            this.isFocusIn = false;
            this.showInputSkill = false;
        },
        handleClick: function () {
            this.showInputSkill = true;
            setTimeout(function () {
                document.getElementById('skill').focus();
            }, 50);
        },
        handleSubmit: function (event) {

            event.preventDefault();
            this.$emit('add-skill', this.skillInput);
            this.skillInput = "";
        },
        deleteTag: function (tag) {
            this.$emit('delete-skill', tag);
        }
    }
}
</script>

<style scoped>
fieldset {
    border-radius: 5px;
    text-align: left;
    border: 1px solid rgb(194, 187, 187);
    margin-bottom: 1rem;
}

.d_input-text>fieldset {
    min-height: 50px;
}

.d_input-text>fieldset>input {
    width: 100%;
    border: none;
}

.d_input-text>fieldset>legend>p {
    margin: 0 0.5rem;
    font-size: 0.875rem;
}

.d_input-text>fieldset>input:focus {
    border: none;
    outline: none;
}

.d_focus-in {
    border: 1px solid purple;
}

.tag-pill {
    display: inline-block;
    background-color: #1867C0;
    color: white;
    padding: 5px 10px;
    border-radius: 10px;
    margin: 2px 2px 2px 2px;
    font-size: 13px;
}

.tag-pill>i {
    cursor: pointer;
}

button {
    visibility: hidden;
}
</style>
