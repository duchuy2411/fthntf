<template>
<div id="section">

    <div class="row-section">

        <div class="section-left">
            <div><strong>{{ section.title }}</strong></div>
        </div>

        <div class="section-right">

            <div    :class="['btn-arrow', {invisible: isMid === 1}]" 
                    @click="clickSectionUp(section)">
                <img src="@/assets/icons8-up-arrow-50.png">
            </div>

            <div    :class="['btn-arrow', {invisible: isMid === 5}]" 
                    @click="clickSectionDown(section)">
                <img src="@/assets/icons8-down-arrow-50.png">
            </div>

            <div class="lbl-edit" id="margin-right-lbl" @click="showModal">Add</div>
        </div>
    </div>

    <div :key="row" v-for="row in section.content">

        <div class="row-section">

            <div class="section-left">
                <div><strong>{{ row.strong }}</strong></div>
                <div>{{ row.para }} </div>
                <div v-if="row.raw_html" v-html="row.raw_html"></div>
            </div>

            <div class="section-right">

                <div    :class="['btn-arrow', {invisible: section.content.indexOf(row) === 0 }]" 
                        @click="clickItemUp(section, row)">
                    <img src="@/assets/icons8-up-arrow-50.png">
                </div>

                <div    :class="['btn-arrow', {invisible: section.content.indexOf(row) === section.content.length - 1}]" 
                        @click="clickItemDown(section, row)">
                    <img src="@/assets/icons8-down-arrow-50.png">
                </div>

                <div class="lbl-edit" @click="showModal()">EDIT</div>
                <div class="lbl-delete" id="margin-right-lbl">DELETE</div>
            </div>
        </div>
    </div>
</div>

</div>
</template>

<script>
export default {
    props: {
        section: Object,
        isMid: Number,
        clickItemUp: Function,
        clickItemDown: Function,
        clickSectionUp: Function,
        clickSectionDown: Function,
        showModal: Function
    }
}
</script>

<style>

</style>
