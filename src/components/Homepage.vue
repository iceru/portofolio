<template>
<div class="home">
    <img class="blob one" src="@/assets/blob1.png" alt="">
    <img class="blob two" src="@/assets/blob2.png" alt="">

    <div class="cta row">
        <div class="col-12 col-md-8">
            <div class="cta-text">
                <h1>Hello, My Name is <span class="purple">Hafiz!</span></h1>
                <h4 class="pt-2">I’m a <span class="purple">UI/UX Designer</span> and <span class="purple">Web Developer</span> from Indonesia.</h4>
                <!-- <h5 class="pt-2">I’m seeking for a new opportunity right now.</h5> -->

                <div class="button-cta d-flex flex-wrap pt-3">
                    <!-- <a href="https://drive.google.com/file/d/1e1eX3JVZlVVU9bLIryOGGGblVqR3Wa4_/view?usp=sharing" class="button-purple mr-2" download="CV Muhamad Hafiz">Download My CV</a> -->
                    <router-link to="/projects" class="button-purple mr-4">Projects</router-link>
                    <router-link to="/contact" class="button-purple">Contact</router-link>
                </div>
            </div>
        </div>
        <div class="col-12 col-md-4">
            <div class="cta-img">
                <img src="@/assets/vector.png" alt="">
            </div>
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
.home {
    position: relative;
    min-height: 77vh;
    padding: 0 2rem;
}
.blob {
    position: absolute;
}

.cta-text h1 {
    font-weight: 600;
    padding-top: 60px;
}

.one {
    width: 400px;
    top: 30%;
    left: 5%;
}

.two {
    width: 350px;
    right: 10px;
    top: 10%;
}

.cta {
    justify-content: space-around;
    padding: 2rem;
}


@media only screen and (max-width: 600px) {
    .cta {
        padding: 50px 5%;
        justify-content: space-between;
        flex-direction: column;
        height: auto;
    }

    .home {
        padding: 0;
        min-height: 70vh;
    }

    .cta-img {
        margin: 30px auto;
        display: none;
    }

    .one {
        display: none
    }

    .two {
        width: 200px;
        right: 5px;
        top: 30%;
    }

}

.cta-img img {
    z-index: 5;
}

.button-purple {
    background: #52a793;
    color: white;
    text-decoration: none;
    border-radius: .5rem;
    padding: 6px 3rem;
    transition: .2s ease-out;
}

.button-purple:hover {
    background: #54d3b5;
    text-decoration: none;
    border-radius: .5rem;
    transition: .2s ease-in;
}
</style>
