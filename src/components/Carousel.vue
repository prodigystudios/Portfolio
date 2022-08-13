<template>
    <transition name="fade">
            <h2 v-if="hasStopped" class="project-title">{{ projectTitle }}</h2>
    </transition>

    <div @mouseover="stop()" @mouseleave="resume()" class="carousel">
        <div class="blur">
            <slot></slot>
        </div>
    </div>
    <div class="btn-container" @mouseover="stop()" @mouseleave="resume()">
        <button @click="prev" class="prev"><img src="../assets/icons//left-arrow-color.png" width="40" height="40"
                alt="prev"></button>
        <button @click="next" class="next"><img src="../assets/icons/right-arrow.png" width="40" height="40"
                alt="next"></button>
    </div>
</template>

<script>
export default {
    props: ['projectTitle'],
    data() {
        return {
            hasStopped: false
        }
    },
    methods: {
        next() {
            this.$emit('next')
            
        },
        prev() {
            this.$emit('prev')
        },
        stop() {
            this.$emit('stop')
            this.hasStopped = true
        },
        resume() {
            this.$emit('resume')
            this.hasStopped = false
        }
    }
}
</script>

<style scoped>
.carousel
{
    position: relative;
    width: 700px;
    height: 400px;
    overflow: hidden;
    border-radius: 10px;
}

.project-title
{
    position: absolute;
    top: 24em;
    left: 57em;

}

.blur:hover
{
    filter: blur(8px);
}

.btn-container
{
    display: flex;
    justify-content: center;
    gap: 50px;
    margin-top: 15px;
}

button
{
    display: flex;
    justify-content: center;
    align-items: center;
    background: white;
    height: fit-content;
    width: fit-content;
    border: none;
}

button:focus,
button:hover
{
    cursor: pointer;
    opacity: 0.75;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

</style>