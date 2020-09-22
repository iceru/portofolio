<template>
<div>
    <img class="blob one" src="@/assets/blob2.png" alt="">
    <img class="blob two" src="@/assets/blob1.png" alt="">

    <div class="cta d-flex">
        <div class="cta-text">
            <h1>Hello, My Name is <span class="purple">Hafiz!</span></h1>
            <h4 class="pt-2">I’m an <span class="purple">UI/UX Designer</span> and <span class="purple">Web Developer</span> from Indonesia.</h4>
            <h5 class="pt-2">I’m seeking for a new opportunity right now.</h5>

            <div class="button-cta d-flex pt-3">
                <a href="https://drive.google.com/file/d/1e1eX3JVZlVVU9bLIryOGGGblVqR3Wa4_/view?usp=sharing" class="button-purple mr-2" download="CV Muhamad Hafiz">Download My CV</a>
                <router-link to="/projects" class="button-purple">Projects</router-link>
            </div>
        </div>
        <div class="cta-img">
            <img src="@/assets/vector.png" alt="">
        </div>
    </div>

</div>
</template>

<script>
export default {
    data() {
        return {
            publicPath: process.env.BASE_URL
        }
    }
}
</script>

<style scoped>
.blob {
    position: absolute;
}

.one {
    width: 400px;
    top: 35%;
    left: 10%;
    z-index: -1;
}

.two {
    width: 350px;
    right: 10%;
    z-index: -1;
    top: 20%;
}

.cta {
    padding: 100px 20%;
    height: 80vh;
    justify-content: space-around;
}

@media only screen and (max-width: 1300px) {
    .cta {
        padding: 100px 5%;
        justify-content: space-between;
    }

    .one {
        width: 350px;
        top: 35%;
        left: 0;
        z-index: -1;
    }

    .two {
        width: 300px;
        right: 0;
        z-index: -1;
        top: 25%;
    }

    footer {
        padding: 20px 5%;
        justify-content: space-between;
    }
}

@media only screen and (max-width: 600px) {
    .cta {
        padding: 50px 5%;
        justify-content: space-between;
        flex-direction: column;
        height: auto;
    }

    .cta-img {
        margin: 30px auto;
    }

    .one {
        display: none;
    }

    .two {
        width: 200px;
        right: 0;
        z-index: -1;
        top: 60%;
    }

}

.cta-img img {
    z-index: 5;
}

.button-purple {
    border: 2px solid #6D59E9;
    background: #6D59E9;
    color: white;
    text-decoration: none;
    border-radius: 30px;
    padding: 6px 12px;
    transition: .2s ease-out;
}

.button-purple:hover {
    border: 2px solid #6D59E9;
    background: white;
    color: #6D59E9;
    text-decoration: none;
    border-radius: 30px;
    padding: 6px 12px;
    transition: .2s ease-in;
}
</style>
