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
                <div class="link-Container">
                    <div v-if="project.githubLink != null" class="links">
                        <a :href="'' + project.githubLink">Länk till github repo</a>
                    </div>
                    <div v-if="project.githublinkApi != null" class="links">
                        <a :href="'' + project.githublinkApi">Länk till github api</a>
                    </div>
                    <div v-if="project.liveSiteLink != null" class="links">
                        <a :href="'' + project.liveSiteLink">Länk till live site</a>
                    </div>
                </div>
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
                    githubLink: 'https://github.com/prodigystudios/todo-api',
                    githublinkApi: 'https://github.com/prodigystudios/TodoApi',
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
                            indepthDescription: "Det här visar hur jag hanterar calls till min api för att spara nya värden till databasen"
                        },
                        {
                            img: require("@/assets/TodoImages/NewUppload/CodeSnipDatabase.png"),
                            indepthDescription: "Här hämtar vi alla poster i min sql databas"
                        },
                        {
                            img: require("@/assets/TodoImages/NewUppload/SnapGetByid.png"),
                            indepthDescription: "Här hämtar vi en specifk post ifrån min databas som har samma id som vi efter frågar"
                        },
                        {
                            img: require("@/assets/TodoImages/NewUppload/snapCreateNewAndDelete.png"),
                            indepthDescription: "Här hanterar vi hur vi sparar nya poster och tar bort poster ifrån databasen"
                        },
                    ]
                },
                {
                    id: 1,
                    projectName: "Blogg app",
                    projectDescription: "En enkel blogg sida där du kan skapa, redigera och ta bort inlägg",
                    githubLink: 'https://github.com/prodigystudios/blogg-with-api',
                    images: [
                        {
                            img: require("@/assets/Blogg/SizeTest.png"),
                            indepthDescription: 'Här ser vi första sidan där alla inlägg kommer listas och även en knapp för att skapa nya inlägg'
                        },
                        {
                            img: require("@/assets/Blogg/NewPostView.png"),
                            indepthDescription: 'Här skapar vi ett nytt inlägg'
                        },
                        {
                            img: require("@/assets/Blogg/ShowPostEdit.png"),
                            indepthDescription: 'Här kan vi redigera eller ta bort inlägg'
                        },
                        {
                            img: require("@/assets/Blogg/CodeSnipOne.png"),
                            indepthDescription: 'CodeSnip: Här visas hur jag tar bort och redigerar inläggen o uppdaterar databasen'
                        },
                        {
                            img: require("@/assets/Blogg/CodeSnipTwo.png"),
                            indepthDescription: 'CodeSnip: Hämta alla inlägg från databasen'
                        },
                    ]
                },
                {
                    id: 2,
                    projectName: "Brödernas clone",
                    projectDescription: "Det här en liten enkel clone av brödernas hemsida",
                    githubLink: "https://github.com/prodigystudios/BrothersCloneWebsite",
                    images: [
                        {
                            img: require("@/assets/BrödernasClone/Home.png"),
                            indepthDescription: 'Här ser vi första sidan med enkla texter som beskriver resturangen',
                        },
                        {
                            img: require("@/assets/BrödernasClone/Menu.png"),
                            indepthDescription: 'Här har vi menyn för veckan'
                        },
                        {
                            img: require("@/assets/BrödernasClone/Contact.png"),
                            indepthDescription: 'en enkel sida där kontakt informationen finns'
                        },
                        {
                            img: require("@/assets/BrödernasClone/codeMenuHtml.png"),
                            indepthDescription: 'html med en vue for loop som skapar element för varje dag'
                        },
                        {
                            img: require("@/assets/BrödernasClone/codeMenuJS.png"),
                            indepthDescription: 'o här har vi lite enkel javascript för att skapa våra object med information som ska visas på hemsidan'
                        },
                    ]
                },
                {
                    id: 3,
                    projectName: "Webshop",
                    projectDescription: "En super enkel webshop! Där du kan se information om produkten med bilder",
                    githubLink: 'https://github.com/prodigystudios/vue-webshop',
                    images: [
                        {
                            img: require("@/assets/Webshop/Home.png"),
                            indepthDescription: 'Här listas alla produkter som finns i våran databas'
                        },
                        {
                            img: require("@/assets/Webshop/ProductView.png"),
                            indepthDescription: 'Här ser vi en bild med information om produkten och ett pris, här kan vi även välja om vi vill köpa produkten'
                        },
                        {
                            img: require("@/assets/Webshop/KöpView.png"),
                            indepthDescription: 'Nu är det dags för betalning! här ser vi information på produkten igen, här fyller vi i information om oss som köper produkten och betalnings informationen'
                        },
                        {
                            img: require("@/assets/Webshop/ProductListCode.png"),
                            indepthDescription: 'Här ser vi koden som gör ett call till våran api som sedan hämtar alla produkter ur databasen och sedan listar dom på sidan'
                        },
                        {
                            img: require("@/assets/Webshop/ProductViewCode.png"),
                            indepthDescription: 'Här hämtar vi informationen ifrån databasen om vald produkt och visar den på sidan'
                        },
                        {
                            img: require("@/assets/Webshop/CartViewCode.png"),
                            indepthDescription: 'Här sparar vi informationen som vi fyller in i vårat formulär för att sedan kunna hantera validering och kontakt till bank'
                        },
                    ]
                },
                {
                    id: 4,
                    projectName: "Väder app",
                    projectDescription: "En enkel lite väder app där du kan se vädret idag och 7 dagar framöver",
                    githubLink: 'https://github.com/prodigystudios/vue-webshop',
                    liveSiteLink: 'https://prodigystudios.github.io/weatherapp/#/',
                    images: [
                        {
                            img: require("@/assets/WheaterApp/Home.png"),
                            indepthDescription: 'Så här ser applikationen ut, väldigt enkel. Här kan du se vädret idag och 7 dagarar framöver, vi ser även ikoner på vilken typ av väder vi får'
                        }
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

.align-text
{
    width: 100%;
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
    outline: var(--clr-hover-link) solid 2px;
    cursor: pointer;
}

.show_image_popup
{
    height: fit-content;
}

.show_image_popup img
{
    width: 1280px;
    height: 500px;
    object-fit:contain;
    border: 2px solid black;
    margin: 10px 0px;
    border-radius: 20px;
    
}

.links
{
    margin-top: 20px;
    padding: 5px;
    text-align: left;
    box-shadow: 1px 1px 1px 1px;
    border-radius: 5px;
    text-align: center;
    font-weight: bold;
}

.links:hover
{
    outline: var(--clr-hover-link);
}

.links a
{
    color: rgb(155, 106, 106);
}

.links a:hover
{
    color: rgba(135, 206, 250, 0.7);
}

.link-Container
{
    display: flex;
    width: 100%;
    gap: 20px;
    flex-wrap: wrap;
}

@media (max-width: 425px)
{
    .show_image_popup img
    {
        max-width: 400px;
    }
}

@media (max-width: 375px)
{
    .show_image_popup img
    {
        max-width: 350px;
    }
}

@media (max-width: 320px)
{
    .show_image_popup img
    {
        max-width: 295px;
    }
}
</style>