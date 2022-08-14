<template>
    <div>
        <div class="main" v-for="project in projects" :key="project.id">
            <div class="container" v-if="tempId == project.id">
                <h1>{{ project.projectName }}</h1>
                <p>{{ project.projectDescription }}</p>
                <transition name="fade">
                <section v-if="!project.isClicked" class="aling-images">
                    <div class="images-container" v-for="(image, i) in images" :key="i">
                        <div>
                            <img @click="project.isClicked = true" class="image-scale" :src="image.img">
                        </div>
                        <p>{{ image.indepthDescription }}</p>
                    </div>
                </section>
                </transition>
            </div>

            <transition name="fade">
                <div v-if="project.isClicked" id="show_image_popup">
                    <div id="image-show-area">
                        <img id="large-image" :src="project.img" alt=""> <!--     popup imge -->
                    </div>
                    <div class="close-btn-area">
                        <button @click="project.isClicked = false" class="close-btn">Stäng</button>
                        <!--     close btn -->
                    </div>
                </div>
            </transition>
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
                    projectName: "Att göra lista",
                    projectDescription: "En att göra lista! Perfekt för dig som har många saker att inte glömma bort väldigt enkel att använda",
                    img: require("@/assets/testTodo.png"),
                    isClicked: false,
                    images: [
                        {
                            img: require("@/assets/testTodo.png"),
                            indepthDescription: 'Det här är min frontend av att göra lista. Du kan lägga till saker att göra via input fältet ' +
                                'Du kan stryka över avslutade uppgfiter ur listan och klicka på x för att ta bort vald uppgift. Eller ta bort allting'
                        },
                        {
                            img: require("@/assets/testTodo.png")
                        },
                        {
                            img: require("@/assets/testTodo.png")
                        },
                    ]
                },
                {
                    id: 1,
                    projectName: "b",
                    projectDescription: "En att göra lista! Perfekt för dig som har många saker att inte glömma bort väldigt enkel att använda",
                    img: require("@/assets/testTodo.png"),
                    images: [
                        {
                            img: require("@/assets/testTodo.png"),
                            indepthDescription: 'Det här är min frontend av att göra lista. Du kan lägga till saker att göra via input fältet ' +
                                'Du kan stryka över avslutade uppgfiter ur listan och klicka på x för att ta bort vald uppgift. Eller ta bort allting'
                        },
                        {
                            img: require("@/assets/testTodo.png")
                        },
                        {
                            img: require("@/assets/testTodo.png")
                        },
                    ]
                },
                {
                    id: 2,
                    projectName: "c",
                    projectDescription: "En att göra lista! Perfekt för dig som har många saker att inte glömma bort väldigt enkel att använda",
                    img: require("@/assets/testTodo.png"),
                    images: [
                        {
                            img: require("@/assets/testTodo.png"),
                            indepthDescription: 'Det här är min frontend av att göra lista. Du kan lägga till saker att göra via input fältet ' +
                                'Du kan stryka över avslutade uppgfiter ur listan och klicka på x för att ta bort vald uppgift. Eller ta bort allting'
                        },
                        {
                            img: require("@/assets/testTodo.png")
                        },
                        {
                            img: require("@/assets/testTodo.png")
                        },
                    ]
                },
                {
                    id: 3,
                    projectName: "Todo app",
                    projectDescription: "En att göra lista! Perfekt för dig som har många saker att inte glömma bort väldigt enkel att använda",
                    img: require("@/assets/testTodo.png"),
                    images: [
                        {
                            img: require("@/assets/testTodo.png"),
                            indepthDescription: 'Det här är min frontend av att göra lista. Du kan lägga till saker att göra via input fältet ' +
                                'Du kan stryka över avslutade uppgfiter ur listan och klicka på x för att ta bort vald uppgift. Eller ta bort allting'
                        },
                        {
                            img: require("@/assets/testTodo.png")
                        },
                        {
                            img: require("@/assets/testTodo.png")
                        },
                    ]
                },
                {
                    id: 4,
                    projectName: "b",
                    projectDescription: "b",
                    img: require("@/assets/testTodo.png"),
                    images: [
                        {
                            img: require("@/assets/testTodo.png"),
                            indepthDescription: 'Det här är min frontend av att göra lista. Du kan lägga till saker att göra via input fältet ' +
                                'Du kan stryka över avslutade uppgfiter ur listan och klicka på x för att ta bort vald uppgift. Eller ta bort allting'
                        },
                        {
                            img: require("@/assets/testTodo.png")
                        },
                        {
                            img: require("@/assets/testTodo.png")
                        },
                    ]
                },
                {
                    id: 5,
                    projectName: "c",
                    projectDescription: "c",
                    img: require("@/assets/testTodo.png"),
                    images: [
                        {
                            img: require("@/assets/testTodo.png"),
                            indepthDescription: 'Det här är min frontend av att göra lista. Du kan lägga till saker att göra via input fältet ' +
                                'Du kan stryka över avslutade uppgfiter ur listan och klicka på x för att ta bort vald uppgift. Eller ta bort allting'
                        },
                        {
                            img: require("@/assets/testTodo.png")
                        },
                        {
                            img: require("@/assets/testTodo.png")
                        },
                    ]
                },
            ],
            tempId: 0
        }
    },
    created() {
        this.tempId = this.$route.params.id
    },
    computed: {
        images: function () {
            var images = []
            for (let i = 0; i < this.projects[this.tempId].images.length; i++) {
                images.push(this.projects[this.tempId].images[i])
            }
            return images
        }
    }
}
</script>

<style scoped>
.main
{
    text-align: center;
}

.aling-images
{
    display: flex;
    gap: 29px;
}

.image-scale
{
    width: 375px;
    height: 400px;
}

.images-container
{
    height: fit-content;
    border: 1px solid black;
    border-radius: 5px;
}

.images-container:hover
{
    outline: rgba(135, 206, 250, 0.7) solid 3px;
    cursor: pointer;
}

#show_image_popup img
{
    max-width: 90%;
    height: auto;
}

.close-btn
{
    width: 100%;
    height: 40px;
    background: rgba(135, 206, 250, 0.7);
    border: none;
    border-radius: 30px;
    cursor: pointer;
}

.close-btn:hover
{
    opacity: 0.9;
    outline: 1px solid black;
}

.fade-enter-active
{
    transition: opacity 1s ease;
}

.fade-leave-active
{
    display: none;
}

.fade-enter-from,
.fade-leave-to
{
    opacity: 0;
}

</style>