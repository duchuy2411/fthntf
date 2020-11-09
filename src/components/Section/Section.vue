<template>
<div class="certificates-ed" id="section">

    <div class="row-section">
        <div class="section-left">
            <div><strong>{{ section.title }} {{isMid}}</strong></div>
        </div>
        <div class="section-right">
            <div class="btn-arrow invisible">
                <img src="@/assets/icons8-up-arrow-50.png">
            </div>
            <div class="btn-arrow">
                <img src="@/assets/icons8-down-arrow-50.png">
            </div>
            <div class="lbl-edit" id="margin-right-lbl">Add</div>
        </div>
    </div>

    <div :key="row" v-for="row in section.content">
        <div class="row-section">
            <div class="section-left">
                <div><strong>{{ row.strong}}</strong></div>
                <div>{{ row.para}} </div>
            </div>
            <div class="section-right">
                <div :class="['btn-arrow', {invisible: section.content.indexOf(row) === 0 }]">
                    <img src="@/assets/icons8-up-arrow-50.png">
                </div>
                <div :class="['btn-arrow', {invisible: section.content.indexOf(row) === section.content.length - 1}]">
                    <img src="@/assets/icons8-down-arrow-50.png">
                </div>
                <div class="lbl-edit">EDIT</div>
                <div class="lbl-delete" id="margin-right-lbl">DELETE</div>
            </div>
        </div>
    </div>

</div>
</template>

<script>
export default {
    props: {
        section: Object,
        isMid: Number
    }
}
</script>

<style>

</style>
