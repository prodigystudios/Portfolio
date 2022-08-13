<template>

    <form @submit.prevent="sendEmail" class="container">
        <div class="contactmetext">
            <h1>Kontakta mig!</h1>
        </div>
        <div class="firstname">
            <input type="text" placeholder="Förnamn" v-model="fname" name="fname">
        </div>
        <div class="lastname">
            <input type="text" placeholder="Efternamn" v-model="lname" name="lname">
        </div>
        <div class="email">
            <input type="email" placeholder="Email" v-model="email" name="email">
        </div>
        <div class="message">
            <textarea type="message" cols="30" rows="5" placeholder="Meddelande" v-model="message"
                name="message"></textarea>
        </div>
        <div class="send">
            <input type="submit" value="Skicka">
        </div>
    </form>
</template>

<script>
import emailjs from 'emailjs-com';
export default {
    name: 'email',

    data() {
        return {
            fname: '',
            lname: '',
            email: '',
            message: ''
        }
    },
    methods: {
        sendEmail(e) {
            try {
                emailjs.sendForm('service_en6yx2f', 'template_tzn6b4j', e.target,
                    'Uf01cgMiidXGxsqS4', {
                    fname: this.fname,
                    lname: this.lname,
                    email: this.email,
                    message: this.message
                })

            } catch (error) {
                console.log({ error })
            }
            // Reset form field
            this.fname = ''
            this.lname = ''
            this.email = ''
            this.message = ''
        },
    }
}
</script>


<style scoped>
h1 {
    margin-top:0;
}
*
{
    box-sizing: border-box;
}

input[type=text],
[type=email],
textarea
{
    width: 100%;
    padding: 12px;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
    margin-top: 6px;
    margin-bottom: 16px;
    background: rgba(173, 216, 230, 0.247);
    resize: none;

}

input[type=submit]
{
    background-color: #4CAF50;
    color: white;
    padding: 12px 20px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    width: 100%;
}

input[type=submit]:hover
{
    background-color: #45a049;
}

.container
{
    display: grid;
    position: relative;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 2fr 2fr 2fr 5fr;
    gap: 0px 29px;
    grid-template-areas:
        "contactmetext contactmetext"
        "firstname lastname"
        "email email"
        "message message"
        "send send";

    margin: auto;
    border-radius: 5px;
    background-color: #f2f2f2;
    padding: 20px;
    width: 100%;
}

.contactmetext
{
    grid-area: contactmetext;
}

.firstname
{
    grid-area: firstname;

}

.lastname
{
    grid-area: lastname;

}

.email
{
    grid-area: email;
}

.message
{
    grid-area: message;

}

.send
{
    grid-area: send;
}

h1
{
    font-weight: normal;
}
</style>