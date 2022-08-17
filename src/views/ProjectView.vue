<template>
    <h1 class="center">Mina projekt!</h1>
    <div class="main-container">
        <div v-for="project in projects" :key="project.id">
            <div class="content-align">
                <router-link :to="'project/' + project.id">
                    <h2>{{ project.projectName }}</h2>
                    <img class="img-scale" :src="project.img" :alt="project.projectName">
                    <h3>{{ project.projectDescription }}</h3>
                    <div class="icons-container">
                        <div class="aling-icons" v-for="(icon, index) in project.icons" :key="index">
                            <img class="scale-icon" :src="icon.icon">
                        </div>
                    </div>

                </router-link>
            </div>
        </div>
    </div>

</template>


<script>
export default {
    data() {
        return {
            projects: [
                {
                    id: 0,
                    projectName: "Todo app",
                    projectDescription: "En att göra lista! Perfekt för dig som har många saker att inte glömma bort väldigt enkel att använda",
                    img: require("@/assets/testTodo.png"),
                    icons: [
                        {
                            icon: require("@/assets/icons/icons8-html-5-32.png"),
                        },
                        {
                            icon: require("@/assets/icons/icons8-css3-32.png"),
                        },
                        {
                            icon: require("@/assets/icons/icons8-sql-32.png"),
                        },
                        {
                            icon: require("@/assets/icons/icons8-c-sharp-logo-32.png"),
                        },
                        {
                            icon: require("@/assets/logo.png"),
                        },
                    ]
                },
                {
                    id: 1,
                    projectName: "b",
                    projectDescription: "En att göra lista! Perfekt för dig som har många saker att inte glömma bort väldigt enkel att använda",
                    img: require("@/assets/testTodo.png"),
                    icons: [
                        {
                            icon: require("@/assets/icons/icons8-html-5-32.png"),
                        },
                        {
                            icon: require("@/assets/icons/icons8-html-5-32.png"),
                        },
                    ]
                },
                {
                    id: 2,
                    projectName: "c",
                    projectDescription: "En att göra lista! Perfekt för dig som har många saker att inte glömma bort väldigt enkel att använda",
                    img: require("@/assets/testTodo.png"),
                    icons: [
                        {
                            icon: require("@/assets/icons/icons8-html-5-32.png"),
                        },
                        {
                            icon: require("@/assets/icons/icons8-html-5-32.png"),
                        },
                    ]
                },
                {
                    id: 3,
                    projectName: "Todo app",
                    projectDescription: "En att göra lista! Perfekt för dig som har många saker att inte glömma bort väldigt enkel att använda",
                    img: require("@/assets/testTodo.png"),
                    icons: [
                        {
                            icon: require("@/assets/icons/icons8-html-5-32.png"),
                        },
                        {
                            icon: require("@/assets/icons/icons8-html-5-32.png"),
                        },
                    ]
                },
            ],
        }
    },
}


</script>
    
<style scoped>
.center
{
    text-align: center;
}

.main-container
{
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
    width: 100%;
    gap: 1em;
    margin-bottom: 20px;
}

.content-align
{
    border: 1px solid black;
    border-radius: 10px;
    gap: 50px;
    padding: 0px 20px;
}

.content-align:hover
{
    outline: rgba(135, 206, 250, 0.7) solid 5px;
}

.content-align a
{
    color: black;
}
.content-align a:hover
{
    color: rgba(135, 206, 250, 0.7);
}

.icons-container
{
    display: flex;
    
}
.scale-icon {
    width:32px;
}

.img-scale
{
    width: 100%;
    height: 100%;
}
</style>