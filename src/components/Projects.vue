<template>
<div class="container">
    <div class="row">
        <div class="col-12" v-for="(project, index) in projects" :key="project.id">
            <div class="project">
                <div class="info justify-content-between">
                    <div class="title text-center">
                        <a :href="project.link" target="_blank">
                            <h3 v-text="project.title"></h3>
                        </a>
                    </div>
                    <div class="d-flex justify-content-center">
                        <p v-show="project.tech.includes('Laravel')" class="laravel logo"> <img src="@/assets/laravel.png" alt=""> Laravel</p>
                        <p v-show="project.tech.includes('Vue')" class="logo"> <img src="@/assets/vuejs.png" alt=""> Vue</p>
                        <p v-show="project.tech.includes('Wordpress')" class="logo"> <img src="@/assets/wordpress.png" alt=""> <span class="wordpress">Word</span>Press</p>
                        <p v-show="project.tech.includes('jQuery')" class="logo"> <img src="@/assets/jquery.png" alt=""></p>
                    </div>
                </div>
                
                <div v-html="project.description" class="description mb-4"></div>
                <div :id="'carousel'+index" class="carousel slide" data-ride="carousel">
                    <p class="status" :class="project.status == 'Deployed' ? 'green' : 'orange'" v-text="project.status"></p>
                    <div class="carousel-inner" role="listbox">
                        <div class="carousel-item" v-for="(image, index) in project.images" :class="index == 0 ? 'active' : '' ">
                            <img :src="require(`@/assets/${image}`)" class="w-100">
                        </div>
                    </div>
                    <a class="carousel-control-prev" :href="'#carousel'+index" role="button" data-slide="prev">
                        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                        <span class="sr-only">Previous</span>
                    </a>
                    <a class="carousel-control-next" :href="'#carousel'+index" role="button" data-slide="next">
                        <span class="carousel-control-next-icon" aria-hidden="true"></span>
                        <span class="sr-only">Next</span>
                    </a>
                </div>
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {
    data: function() {
        return {
            projects: 
            [
                {
                    id: 1,
                    title: 'Early Theory',
                    link: 'https://earlytheory.com',
                    status: 'Deployed',
                    tech: ['Laravel', 'jQuery'],
                    images: ['et1.jpg', 'et2.png', 'et3.png']
                },
                {
                    id: 2,
                    title: 'So-Klin',
                    link: '#',
                    status: 'On Development',
                    tech: ['Wordpress', 'jQuery'],
                    images: ['sk1.jpg', 'sk2.png', 'sk3.png']
                },
                {
                    id: 3,
                    title: 'Burn Support Group',
                    link: 'http://burnsupport.id',
                    status: 'Deployed',
                    tech: ['Laravel', 'jQuery'],
                    images: ['bs1.png', 'bs2.png', 'bs3.png']
                },
                {
                    id: 4,
                    title: 'Senimart',
                    link: 'https://senimart.id',
                    status: 'Deployed',
                    tech: ['Laravel', 'jQuery'],
                    images: ['sm1.png', 'sm2.png', 'sm3.png']
                },
                {
                    id: 5,
                    title: 'Asia Stem Cell Center',
                    link: 'https://asiastemcellcenter.com',
                    status: 'Deployed',
                    tech: ['Wordpress'],
                    images: ['asc1.jpg', 'asc2.png', 'asc3.png']
                },
                {
                    id: 5,
                    title: 'Hardwarenesia',
                    link: 'https://asiastemcellcenter.com',
                    status: 'On Development',
                    tech: ['Vue'],
                    images: ['hw1.png', 'hw2.jpg']
                },
            ]
        }
    },
}
</script>

<style>

.col-md-6:nth-child(odd) {
    padding-right: 3rem;
}

.col-md-6:nth-child(even) {
    padding-left: 3rem;
}

.project {
    margin: auto;
    margin-bottom: 5rem;
    width: 70%;
    position: relative;
}

.project a:hover {
    color: #52a793;
    transition: .2s ease-in;
}

.project:after {
    width: 60%;
    height: 1px;
    content: '';
    background-color: #dddddd;
    position: absolute;
    bottom: -2.5rem;
    left: 50%;
    transform: translateX(-50%);
}

a:hover {
    text-decoration: none;
}

.carousel {
    border: 1px solid rgba(0, 0, 0, 0.3);
    border-radius: .5rem;
    margin: auto;
}

.carousel-item {
    height: 56.25%;
}

.carousel-item img {
    object-fit: cover;
    border-radius: .5rem;
    object-position: top;
}


.info {
    align-items: center;
    margin-bottom: .5rem;
    display: flex;
}

.info h3 {
    font-weight: 700;
    margin: 0;
}

.satu {
    border-right: 2px solid #041E42;
    padding-right: 30px;
    margin-left: 0;
}

.title {
    align-items: center;
}

.title a {
    color: #384857;
    transition: all .2s ease-in;
}

.title a:hover {
    color: #52a793;
    transition: all .2s ease-in;
}

.logo {
    padding: 5px 10px;
    font-weight: bold;
    margin-left: 1rem;
    padding-right: 0;
    height: 34px;
    display: flex;
    align-items: center;
    font-size: 1.5rem;
}

.logo img {
    height: 25px;
    width: auto;
    padding-right: .5rem;
}

@media only screen and (max-width: 600px) {
    .line {
        flex-direction: column;
    }

    .project {
        width: 95%;
        margin-bottom: 4rem;
    }
    
    .project:after {
        bottom: -2rem;
    }

    .info {
        align-items: flex-start;
        display: block;
        margin-bottom: 1.5rem;
    }

    .title {
        flex-direction: column;
        align-items: flex-start;
        margin-bottom: .5rem;
    }

    .logo {
        margin-left: 0;
        margin: 5px 0;
        height: 24px;
        font-size: 1.15rem;
    }

    .logo img {
        height: 18px;
    }

    .carousel-item img {
        object-fit: contain;
    }

    .satu {
        width: 100%;
        border-right: none;
    }

    .dua {
        width: 100%;
        margin-left: 0;
    }

}

.wordpress {
    color: #4783AF;
}

p {
    margin-bottom: 0;
}
.laravel {
    color: #FF2D20;
}

.status {
    border-radius: 30px;
    padding: 5px 10px;
    color: white;
    font-size: .85rem;
    position: absolute;
    top: 10px;
    right: 10px;
    z-index: 15;
    opacity: .9;
}

.green {
    background: #4CC62E;
}

.orange {
    background: #ECAD4E;
}


</style>
