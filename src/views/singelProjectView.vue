<template>
    <div>
        <div class="main" v-for="project in projects" :key="project.id">
            <div class="container" id="focus-picture" v-if="tempId == project.id">
                <h1>{{ project.projectName }}</h1>
                <p>{{ project.projectDescription }}</p>

                <section class="aling-images">
                    <div v-if="tempId == project.id" class="show_image_popup">
                        <div class="image-show-area">
                            <img class="large-image" :src="currentSelectedImage" alt="">
                            <div class="align-text">
                                 <h3>{{ currentSelectedImageInfo }}</h3>
                            </div>
                        </div>
                    </div>
                    <div class="images-container" v-for="(image, i) in images" :key="i">
                        <img @click="selectedImage(i)" class="image-scale" :src="image.img">
                    </div>
                </section>
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
                    projectName: "To do app",
                    projectDescription: "Perfekt för dig som behöver lista saker du behöver göra så du inte glömmer bort!",
                    isClicked: false,
                    images: [
                        {
                            img: require("@/assets/TodoImages/NewUppload/adobe/MainPage.png"),
                            indepthDescription: 'Här ser du hur sidan ser ut med saker att göra i en lista, Du kan lägga till nya uppgifter genom att fylla i fältet'
                        },
                        {
                            img: require("@/assets/TodoImages/NewUppload/adobe/MainPageCompleted.png"),
                            indepthDescription: "Frontend som visar hur de ser ut när uppgifterna är klara!"
                        },
                        {
                            img: require("@/assets/TodoImages/NewUppload/TodoGetFromApi.png"),
                            indepthDescription: "Det här visar hur jag hanterar calls till min api för att hämta och ta bort värden ur min databas"
                        },
                        {
                            img: require("@/assets/TodoImages/NewUppload/TodoSaveCodeSnip.png"),
                            indepthDescription: "Det här visar hur jag hanterar calls till min databas för att spara nya värden"
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
            tempId: 0,
            currentSelectedImage: '',
            currentSelectedImageInfo: "",
        }
    },
    created() {
        this.tempId = this.$route.params.id
        this.currentSelectedImage = this.projects[this.tempId].images[0].img
        this.currentSelectedImageInfo = this.projects[this.tempId].images[0].indepthDescription
    },
    computed: {
        images: function () {
            var images = []
            for (let i = 0; i < this.projects[this.tempId].images.length; i++) {
                images.push(this.projects[this.tempId].images[i])
            }
            return images
        },
    },
    methods: {
        selectedImage(id) {
            this.currentSelectedImage = this.projects[this.tempId].images[id].img
            this.currentSelectedImageInfo = this.projects[this.tempId].images[id].indepthDescription
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
    flex-wrap: wrap;
    gap: 10px;
}

.align-text {
}
.images-container
{
    width: 100px;
    height: fit-content;
    border: 1px solid black;
    border-radius: 5px;
}

.image-scale
{
    object-fit: contain;
    width: 100px;
    height: 100px;
}

.images-container:hover
{
    outline: rgba(135, 206, 250, 0.7) solid 3px;
    cursor: pointer;
}

.show_image_popup {
    height: fit-content;
}

.show_image_popup img
{
    width: 1280px;
    height: 700px;
    object-fit: contain;
    border: 2px solid black;
    margin: 10px 0px;
    border-radius: 20px;
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