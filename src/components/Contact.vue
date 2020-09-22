<template>
<div class="contact d-flex justify-content-around">
    <div class="contact-text">
        <h1>Contact <br> Information</h1>
        <div class="d-flex align-items-center mt-4 purple">
            <i class="fas fa-phone-alt mr-2"></i>
            <p>+6285771074950</p>
        </div>
        <div class="d-flex align-items-center mt-4 purple">
            <i class="fas fa-envelope mr-2"></i>
            <p>m.hafiz1825@gmail.com</p>
        </div>
    </div>

    <div class="contact-mail">
        <!--<h3>Get In Touch</h3>
        <hr>
        <div v-if="show_contact == true">
            <div v-if="contact_notice !=  ''" class="alert alert-warning">
                {{ contact_notice }}
            </div>
            <form @submit.prevent="sendContactMessage()">
                <div class="form-group">
                    <label for="">Email</label>
                    <input v-model="contact_email" type="text" class="form-control" name="" id="" aria-describedby="helpId" placeholder="">
                </div>
                <div class="form-group">
                    <label for="">Messages</label>
                    <textarea v-model="contact_message" class="form-control" name="" id="" rows="4"></textarea>
                </div>
                <button type="submit" class="button-white">Submit</button>
            </form>
        </div>
        <div v-else>
            <h3>Message Sent Successfully!</h3>
            <p>Thank you for contacting us, we'll get back to you as soon as we can.</p>
        </div>-->
    </div>
</div>
</template>

<script>
export default {

}
</script>

<style>
.contact {
    padding: 100px 20%;
    height: 80vh;
}

.contact-text {
    font-size: 1.2em
}

p {
    margin: 0;
}

.contact-mail {
    color: white;
    padding: 40px 50px;
    border-radius: 30px;
}

.form-group {
    width: 400px
}

@media only screen and (max-width: 600px) {
    .contact {
        flex-direction: column;
        padding: 50px 5%;
    }

    .contact-text {
        margin-bottom: 30px;
    }

    .form-group {
        width: 320px;
    }
}

hr {
    border: 1px solid white;
    width: 30%;
    margin-left: 0;
}

h1,
h3 {
    font-weight: bold;
}

.form-control {
    border-radius: 15px !important;
}

small {
    color: white;
}

.button-white {
    border: 2px solid #6D59E9;
    background: white;
    color: #6D59E9;
    text-decoration: none;
    border-radius: 10px;
    padding: 10px 20px;
    transition: .2s ease-out;
}

.button-white:hover {
    border: 2px solid #6D59E9;
    background: #6D59E9;
    color: white;
    text-decoration: none;
    border-radius: 10px;
    padding: 10px 20px;
    transition: .2s ease-in;
}
</style>
