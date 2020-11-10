<template>
<div class="content">
    <div class="container-content">

        <div class="btn-spin">
            <div class="edit">EDITOR</div>
            <div class="preview">PREVIEW</div>
        </div>

        <div class="csv">
            <button>IMPORT FROM CSV</button>
            <button>DOWNLOAD PDF</button>
        </div>

        <div class="container-editor">

            <ProfileSection :showModal="handleShowModal" />

            <OverviewSection :showModal="handleShowModal" :content="arrayComponent[0].content[0].para" />

            <div v-bind:key="comp" v-for="comp in arrayComponent">

                <Section v-if="comp.title !== `Professional Overview`" :section="comp" :isMid="arrayComponent.indexOf(comp)" :clickSectionUp="handleSectionUp" :clickSectionDown="handleSectionDown" :clickItemUp="handleItemUp" :clickItemDown="handleItemDown" :showModal="handleShowModal" />

            </div>
        </div>
    </div>

        <Modal v-if="showModal" :modalName="nameModal" :data="dataFilter"  @hide-modal="handleHideModal" />

</div>
</template>

<script>
import Section from './Section/Section'
import ProfileSection from '@/components/Section/ProfileSection'
import OverviewSection from '@/components/Section/OverviewSection'
import Modal from '@/components/Popup/ShowModal.vue'

export default {

    components: {
        Section,
        ProfileSection,
        OverviewSection,
        Modal
    },

    data() {
        return {
            arrayComponent: [{
                    title: "Professional Overview",
                    content: [{
                        strong: "",
                        para: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incclassclassunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupclassatat non proclassent, sunt in culpa qui officia deserunt mollit anim class est laborum"
                    }]
                },
                {
                    title: "Certificates",
                    content: [{
                            strong: "AWS Solution Architect - Professional",
                            para: "Amazon (2020)"
                        },
                        {
                            strong: "AWS Solution Architect - Professional",
                            para: "Amazon (2019)"
                        },
                        {
                            strong: "AWS Solution Architect - Associate",
                            para: "Amazon (2020)"
                        }
                    ]
                },
                {
                    title: "Skills",
                    content: [{
                            strong: "Back-end",
                            para: "Java, Python"
                        },
                        {
                            strong: "Front-end",
                            para: "HTML/CSS, Javascript, jQuery, Bootstrap, VueJs"
                        },
                        {
                            strong: "Database",
                            para: "MySQL, Postgre, MongoDB"
                        }
                    ]
                },
                {
                    title: "Work History",
                    content: [{
                            strong: "Senior Developer",
                            para: "HTV - Ho Chi Minh 2020"
                        },
                        {
                            strong: "Developer",
                            para: "ABC - Ho Chi Minh 2020"
                        },
                        {
                            strong: "Junior Developer",
                            para: "XYZ - Ho Chi Minh 2020"
                        }
                    ]
                },
                {
                    title: "Education",
                    content: [{
                            strong: "HCM University of Science",
                            para: "2017 - 2013 | Major: Computer Science"
                        },
                        {
                            strong: "HCM University of Science",
                            para: "2017 - 2013 | Major: Computer Science"
                        }
                    ]
                },
                {
                    title: "Project",
                    content: [{
                            strong: "Project One (Oct 2020 - May 2020)",
                            para: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
                            raw_html: `
                        <div class="project-content">
                        <div><strong>Role: </strong> Team Leader</div>
                        <div><strong>Responsibility: </strong>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. </div>
                        <div><strong>Team size: </strong>5</div>
                        <div><strong>Technologies: </strong>Python, VueJS, Postgres</div>`
                        },
                        {
                            strong: "Project two (Oct 2020 - May 2020)",
                            para: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
                            raw_html: `
                        <div class="project-content">
                        <div><strong>Role: </strong> Team Leader</div>
                        <div><strong>Responsibility: </strong>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. </div>
                        <div><strong>Team size: </strong>5</div>
                        <div><strong>Technologies: </strong>Python, VueJS, Postgres</div>`
                        }
                    ]
                }
            ],
            showModal: false,
            nameModal: "",
            dataFilter: null
        }
    },

    methods: {
        handleSectionUp: function (sectionObject) {
            const indexSection = this.arrayComponent.indexOf(sectionObject);
            console.log(indexSection);

            const newArray = [...this.arrayComponent];
            let temp = newArray[indexSection - 1];
            newArray[indexSection - 1] = newArray[indexSection]
            newArray[indexSection] = temp

            this.arrayComponent = newArray
        },
        handleSectionDown: function (sectionObject) {
            const indexSection = this.arrayComponent.indexOf(sectionObject);
            console.log(indexSection);

            const newArray = [...this.arrayComponent];
            let temp = newArray[indexSection + 1];
            newArray[indexSection + 1] = newArray[indexSection]
            newArray[indexSection] = temp

            this.arrayComponent = newArray
        },
        handleItemUp: function (section, item) {
            const indexSection = this.arrayComponent.indexOf(section);
            const indexItem = this.arrayComponent[indexSection].content.indexOf(item);
            console.log(indexSection, " ", indexItem);

            let newArray = [...this.arrayComponent];
            let newSection = [...newArray[indexSection].content];

            let temp = newSection[indexItem - 1]
            newSection[indexItem - 1] = newSection[indexItem];
            newSection[indexItem] = temp

            newArray[indexSection].content = newSection;

            this.arrayComponent = newArray;
        },
        handleItemDown: function (section, item) {
            const indexSection = this.arrayComponent.indexOf(section);
            const indexItem = this.arrayComponent[indexSection].content.indexOf(item);
            console.log(indexSection, " ", indexItem);

            let newArray = [...this.arrayComponent];
            let newSection = [...newArray[indexSection].content];

            let temp = newSection[indexItem + 1]
            newSection[indexItem + 1] = newSection[indexItem];
            newSection[indexItem] = temp

            newArray[indexSection].content = newSection;

            this.arrayComponent = newArray;
        },
        handleShowModal: function (modal, row) {
            this.showModal = true;
            this.nameModal = modal;
            row ? this.dataFilter = row : this.dataFilter = null;
        },
        handleHideModal: function () {
            this.showModal = false;
            console.log(this.showModal);
        }
    },
}
</script>

<style>
.content {
    float: right;
    background-color: gainsboro;
    width: 85%;
}

.content .container-content {
    padding: 27px 278px;
    width: 100%;
    display: flex;
    align-items: center;
    flex-direction: column;
}

.btn-spin {
    min-width: 280px;
    display: flex;
    background-color: #ffffff;
    justify-content: space-between;
    padding: 5px 1px;
    border-radius: 50px;
}

.btn-spin div {
    border-radius: 29px;
    padding: 10px 30px;
    margin: 0 5px;
    /* border: 1px solid #1867C0; */
    cursor: pointer;
}

.edit {
    color: white;
    background-color: #1867C0;
}

.preview {
    color: #1867C0;
}

.csv {
    margin-top: 70px;
    align-self: flex-end;
}

.csv button {
    padding: 10px 30px;
    border-radius: 5px;
    border: 1px solid #1867C0;
    color: #1867C0;
    background-color: white;
    cursor: pointer;
}

.container-editor {
    margin: 10px 0;
    background-color: gainsboro;
    width: 100%;
}

.row {
    display: block;
}

.btn-edit {
    color: #1867C0;
}

#section {
    background-color: white;
    border-radius: 5px;
    margin: 14px 0 0 0;
}

table {
    width: 100%;
}

#section .row-section {
    display: flex;
    justify-content: space-between;
    border-top: 1px solid gainsboro;
}

.section-left {
    max-width: 90%;
}

.section-right {
    display: flex;
}

.section-right {
    justify-content: flex-end;
    align-items: center;
    text-align: right;
}

.section-right div {
    margin: 0 15px 0 0;
    width: 30px;
}

.section-left img {
    float: left;
    border-radius: 50%;
}

.row-section {
    padding: 15px;
    margin: 0px;
}

.profile-detail {
    float: left;
    margin: 0px 20px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    height: 100%;
}

.profile-detail .lbl-info {
    font-size: 13px;
    margin: 3px 0 0 0;
}

.profile-detail div strong {
    font-size: 18px;
}

.lbl-edit {
    color: #1867C0;
    cursor: pointer;
    margin-right: 0px;
}

.lbl-delete {
    color: #F44336;
    cursor: pointer;
}

.btn-arrow {
    color: #1867C0;
    min-width: 25px;
    min-height: 25px;
    border: 1px solid #1867C0;
    border-radius: 5px;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
}

.btn-arrow:hover {
    background-color: rgb(238, 238, 238);
}

.btn-arrow img {
    color: #1867C0;
    width: 15px;
    height: 15px;
    outline-color: #1867C0;
}

#margin-right-lbl {
    width: 55px;
    margin-right: 0px;
}

#lbl-edit-profile {
    margin: 0;
}

.invisible {
    visibility: hidden;
}

.project-name {
    margin: 5px 0 10px 0px;
}

.project-content {
    margin: 10px 0 0 0;
    font-size: 14px;
}
</style>
