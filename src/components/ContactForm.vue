<template>
    
    <div v-if="emailSent" class="email-notice">
        <h1>Tack för ditt mail!</h1>
        <h3>Jag återkommer så fort jag kan!</h3>
        <button @click="emailSent = false" class="notice-btn">Stäng!</button>
    </div>
    <form @submit.prevent="sendEmail" class="container">
        <div class="contactmetext">
            <h1>Kontakta mig!</h1>
        </div>
        <div class="firstname">
            <input type="text" placeholder="Förnamn" title="Måste vara minst 1 bokstav långt" required="required"
                pattern="[a-Z]{1,20} " v-model="fname" name="fname">
        </div>
        <div class="lastname">
            <input type="text" placeholder="Efternamn" required="required" pattern="[a-zA-Z]{1,20}" v-model="lname"
                name="lname">
        </div>
        <div class="email">
            <input type="email" placeholder="Email" required="required" v-model="email" name="email">
        </div>
        <div class="message">
            <textarea type="message" cols="30" rows="5" placeholder="Meddelande" required="required"
                title="Meddelandet får inte vara längre än 250 bokstäver" pattern="[a-Z 1-9]{1,250}" v-model="message"
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
            message: '',
            emailSent: false
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
                this.emailSent = true;
            } catch (error) {
                console.log({ error })
                this.emailSent = false;
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
h1
{
    margin-top: 0;
}

*
{
    box-sizing: border-box;
}

input[type=text],
[type=email]
{
    width: 100%;
    height: 40px;
    padding: 12px;
    border-radius: 4px;
    box-sizing: border-box;
    margin-top: 6px;
    margin-bottom: 16px;
    background: rgba(173, 216, 230, 0.247);
    resize: none;
}

input[type=text],
textarea
{
    width: 100%;
    background: rgba(173, 216, 230, 0.247);
    resize: none;
    border-radius: 4px;
    box-sizing: border-box;
    border: 1px solid #ccc;
    padding: 12px;
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

input:invalid
{
    border: red;
}

.email-notice
{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    row-gap: 10%;
    width: 60%;
    height: 50%;
    background: rgba(0, 0, 0, 0.90);
    color: white;
    font-size: 20px;
    position: absolute;
    left: 20%;
    z-index: 100;
    text-align: center;
    margin: 0;
    border-radius: 10px;
}

.notice-btn
{
    height: 10%;
    width: 15%;
    background: var(--clr-hover-link);
    border: none;
    border-radius: 15px;
}

.notice-btn:hover
{
    cursor: pointer;
    background: var(--clr-hover-link-Bright);
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
    padding: 30px;
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