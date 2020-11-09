<template>
<div id="search">
    <div><strong>HISTORY REVISION</strong></div>
    <div class="box-revision">
        <div>
            <div><strong>Untitled Revision</strong></div>
            <div class="revision-time">20 minutes ago</div>
        </div>
        <i><img wclassth="15px" height="15px" src='@/assets/icons8-down-arrow-50.png'></i>
    </div>
    <div>
        <button class="btn-review">REVIEW</button>
        <button class="btn-restore btn-blue">RESTORE</button>
    </div>

    <div class="container-revision">
        <div class="box-revision">
            <div>
                <div><strong>Untitled Revision</strong></div>
                <div class="revision-time">20 minutes ago</div>
            </div>
            <i><img wclassth="15px" height="15px" src="@/assets/icons8-down-arrow-50.png"></i>
        </div>
    </div>
    <div class="container-revision">
        <div class="box-revision">
            <div>
                <div><strong>Untitled Revision</strong></div>
                <div class="revision-time">20 minutes ago</div>
            </div>
            <i>
                <img wclassth="15px" height="15px" src="@/assets/icons8-down-arrow-50.png" />
            </i>
        </div>
    </div>
</div>
</template>

<script>
export default {
    data() {
        return {

        }
    }
}
</script>

<style>
#search {
    float: left;
    padding: 13px 15px;
    border-top: 1px solid gainsboro;
    width: 15%;
}

#search .lbl-search-inp {
    font-size: 12px;
    margin: 5px 0 0 0;
}

#search .select-cus {
    background-color: white;
}

.head-content {
    height: 50px;
    display: flex;
    justify-content: space-between;
}

.inp-button {
    border-style: none none solid none;
    width: 100%;
    margin: 0px auto;
    background-color: white;
    padding: 7px 0px 10px 0px;
    font-size: 16px;
}

.lbl-history {
    font-weight: bold;
}

.box-revision {
    margin-top: 10px;
    font-size: 12px;
    display: flex;
    justify-content: space-between;
}

.box-revision .revision-time {
    font-size: 12px;
    color: gainsboro;
}

.box-revision i {
    align-self: center;
}

.btn-restore {
    width: 47%;
    padding: 5px 15px;
    margin: 3px 3px;
    height: 36px;
    border-radius: 5px;
    border-color: #1867C0;
    color: white;
    background-color: #1867C0;
    cursor: pointer;
}

.btn-review {
    color: #1867C0;
    border: 1px solid #1867C0;
    width: 47%;
    height: 36px;
    padding: 5px 15px;
    border-radius: 5px;
    background-color: white;
    cursor: pointer;
}
</style>
