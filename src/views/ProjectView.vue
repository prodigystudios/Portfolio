<template>
    <h1 class="center">Mina projekt!</h1>
    <div class="main-container">
        <div v-for="project in projects" :key="project.id">
            <div class="content-align">
                <router-link :to="'project/' + project.id">
                    <h2>{{ project.projectName }}</h2>
                    <img class="img-scale" :src="project.img" :alt="project.projectName">
                    <div class="spacing">
                        <h3>{{ project.projectDescription }}</h3>
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
                    img: require("@/assets/testTodo.png")
                },
                {
                    id: 1,
                    projectName: "b",
                    projectDescription: "En att göra lista! Perfekt för dig som har många saker att inte glömma bort väldigt enkel att använda",
                    img: require("@/assets/testTodo.png")
                },
                {
                    id: 2,
                    projectName: "c",
                    projectDescription: "En att göra lista! Perfekt för dig som har många saker att inte glömma bort väldigt enkel att använda",
                    img: require("@/assets/testTodo.png")
                },
                {
                    id: 3,
                    projectName: "Todo app",
                    projectDescription: "En att göra lista! Perfekt för dig som har många saker att inte glömma bort väldigt enkel att använda",
                    img: require("@/assets/testTodo.png")
                },
                {
                    id: 4,
                    projectName: "b",
                    projectDescription: "b",
                    img: require("@/assets/testTodo.png")
                },
                {
                    id: 5,
                    projectName: "c",
                    projectDescription: "c",
                    img: require("@/assets/testTodo.png")
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
    display: flex;
    flex-wrap: wrap;
    gap: 80px;
    row-gap: 10px;
    width: 100%;
    margin-bottom: 20px;
}

.content-align
{
    display: flex;
    flex-direction: column;
    text-align: center;
    border: 1px solid black;
    border-radius: 10px;
    height: 500px;
    width: 300px;
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
    width:100%
}

.content-align a:hover
{
    color: rgba(135, 206, 250, 0.7);
}

.img-scale
{
    width: 100%;
    height: 100%;
}
</style>