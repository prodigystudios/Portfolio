<template>
    <div>
        <img class="img-top" src="../assets/ContactMePicture.jpg" height="450" alt="Contact">
    </div>
    <ContactForm />
</template>

<script>
import ContactForm from '@/components/ContactForm.vue';
export default {
    components: {
        ContactForm,
    },
}
</script>

<style scoped>
.img-top
{
    width: 100%;
    margin-top: 20px;
    margin-bottom: 5px;
    border-radius: 10px;
    box-shadow: 1px 2px black;
    
}
</style>