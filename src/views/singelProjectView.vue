<template>
    <div class="main" v-for="project in projects" :key="project.id">
        <div class="container" v-if="tempId == project.id">
            <h1>{{ project.projectName }}</h1>
            <img :src="project.img">
            <p>{{ project.projectDescription }}</p>
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
            tempId: 0
        }
    },
    created() {
        this.tempId = this.$route.params.id
    }
}
</script>

<style scoped>
.main
{
    text-align: center;
}
</style>