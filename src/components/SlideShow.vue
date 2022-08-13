<template>
    <div class="slider-wrapper">
        <div class="slider">
            <div class="front"></div>
            <div class="back"></div>
            <div class="right"></div>
            <div class="left"></div>
        </div>
        <div class="aling-btn">
            <button @click="leftSide()">left</button>
            <button @click="rightSide()">right</button>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            Change: 0,
            interval: null,
        }
    },
    methods: {
        leftSide() {
            this.Change += 90;
            document.querySelector('.slider').style.transform =
                `perspective(800px) rotateX(270deg) rotate(${this.Change}deg) translateZ(-150px)`
        },
        rightSide() {
            this.Change -= 90;
            document.querySelector('.slider').style.transform =
                `perspective(800px) rotateX(270deg) rotate(${this.Change}deg) translateZ(-150px)`
        }
    },
    created() {

        this.interval = setInterval(() => {
            this.Change -= 90;
            document.querySelector('.slider').style.transform =
                `perspective(800px) rotateX(270deg) rotate(${this.Change}deg) translateZ(-150px)`
        }, 5000)
    },
    unmounted() {
        clearInterval(this.interval)
    }
}
</script>

<style scoped>
.slider
{
    width: 400px;
    height: 400px;
    background: dodgerblue;
    transform: perspective(800px) rotateX(270px) rotateY(0deg) translateZ(180deg);
    transform-style: preserve-3d;
    transition: 500ms;
}
.aling-btn {
    display:flex;
    justify-content: center;
}
.front,
.back,
.left,
.right
{
    width: 100%;
    height: 300px;
    position: absolute;
    box-shadow: 0 0 5px #ccc, inset 0 0 10px #ddd;
    border-radius: 10px;
}

.front
{
    transform: rotateX(90deg) translate3d(0, 150px, 150px);
    background: url('../assets/ContactMePicture.jpg');
    background-size: 125%;
}

.back
{
    transform: rotateX(90deg) translate3d(0, 150px, -250px);
    background: url('../assets/MainPagePicture.jpg');
    background-size: 125%;

}

.left
{
    transform: rotateX(90deg) rotateY(90deg) translate3d(50px, 150px, -200px);
    background: url('../assets/ContactMePicture.jpg');
    background-size: 125%;
}

.right
{
    transform: rotateX(90deg) rotateY(90deg) translate3d(50px, 150px, 200px);
    background: url('../assets/MainPagePicture.jpg');
    background-size: 125%;

}

button
{
    padding: 7px 13px;
    width: fit-content;
    border: none;
    border-radius: 5px;
    text-transform: uppercase;
    text-shadow: 0 0 5px #666;
    box-shadow: 0 0 3px #777;
    font-size: 20px;
    background: #41b883;
    color: #fff;
    margin-left: 10px;
    transition: 100ms;
}
</style>