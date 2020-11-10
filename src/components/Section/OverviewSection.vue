<template>
<div class="overview-ed" id="section">

    <div class="row-section">
        <div class="section-left">
            <div><strong>Professional Overview</strong></div>
        </div>
        <div class="section-right">
            <div class="lbl-edit" id="margin-right-lbl">Edit</div>
        </div>
    </div>

    <div class="row-section">
        <div class="section-left">
            {{ content }}
        </div>
    </div>

</div>
</template>

<script>
export default {
    props : {
        content: String
    },

}
</script>

<style>

</style>
