<template>
  <div class="container">
    <div class="row">
      <div class="col-12" v-for="(project, index) in projects" :key="project">
        <div class="project">
          <div class="info justify-content-between">
            <div class="title text-center">
              <a :href="project.link" target="_blank">
                <h3>{{ index + 1 }}. {{ project.title }}</h3>
              </a>
            </div>
            <div class="d-flex justify-content-center">
              <p v-show="project.tech.includes('Laravel')" class="laravel logo">
                <img src="@/assets/laravel.png" alt="" /> Laravel
              </p>
              <p v-show="project.tech.includes('React')" class="react logo">
                <img src="@/assets/react-1.svg" alt="" /> React
              </p>
              <p v-show="project.tech.includes('Vue')" class="logo">
                <img src="@/assets/vuejs.png" alt="" /> Vue
              </p>
              <p v-show="project.tech.includes('HTML')" class="logo html">
                <img src="@/assets/html.png" alt="" /> HTML
              </p>
              <p v-show="project.tech.includes('CSS')" class="logo css">
                <img src="@/assets/css.png" alt="" /> CSS
              </p>
              <p v-show="project.tech.includes('Wordpress')" class="logo">
                <img src="@/assets/wordpress.png" alt="" />
                <span class="wordpress">Word</span>Press
              </p>
              <p v-show="project.tech.includes('jQuery')" class="logo">
                <img src="@/assets/jquery.png" alt="" />
              </p>
            </div>
          </div>

          <div
            v-html="project.description"
            class="description mb-4 mt-3 text-justify"
          ></div>
          <div class="carousel-container">
            <p
              class="status"
              :class="project.status == 'Deployed' ? 'green' : 'orange'"
              v-text="project.status"
            ></p>
            <VueSlickCarousel :arrows="true" :dots="true">
              <div
                class="embed-responsive embed-responsive-16by9"
                v-for="(image, index) in project.images"
                :key="index"
                :class="index == 0 ? 'active' : ''"
              >
                <img
                  class="embed-responsive-item"
                  :src="require(`@/assets/${image}`)"
                  loading="lazy"
                />
              </div>
            </VueSlickCarousel>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
// optional style for arrows & dots
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";

export default {
  name: "Projects",
  components: { VueSlickCarousel },
  data: function() {
    return {
      projects: [
        {
          title: "Travel, Point of Interests and Experiences (V3 Leisure)",
          link: "https://harmonious-taiyaki-4467fa.netlify.app/",
          description:
            "This is an ongoing project to make a user interface for booking accommodation, activities, restaurants, and products. Also, an interactive map combined with a guide on Points of Interest and Experiences. The website is based on Vue.js and integrated with V3 Leisure OBX (Open Booking Exchange) Service",
          status: "Ongoing",
          tech: ["Vue"],
          images: ["poi-1.png"]
        },
        {
          title: "Visit Nara Booking Page",
          link: "https://book.visitnara.jp/",
          description:
            "Visit Nara Booking Page is a project of making the user interface for booking accommodation, activities, restaurants, and products of Visit Nara website. The website is based on React.js and integrated with V3 Leisure OBX (Open Booking Exchange) Service",
          status: "Deployed",
          tech: ["React"],
          images: ["nara-1.png", "nara-2.png", "nara-3.png"]
        },
        {
          title: "Ako Mag Booking Page",
          link: "https://book.ako-mag.jp",
          description:
            "Ako Mag Booking Page is a project of making the user interface for booking accommodation, activities, restaurants, and products of Ako Mag. The website is based on React.js and integrated with V3 Leisure OBX (Open Booking Exchange) Service.",
          status: "Deployed",
          tech: ["React"],
          images: ["ako-1.png", "ako-2.png", "ako-3.png"]
        },
        {
          title: "Panda of Borderlands",
          link: "https://pandaofborderlands.com/",
          description:
            "Panda of Borderlands is a NFT website to introduce the NFT Project. The website is built using React.js",
          status: "Deployed",
          tech: ["React"],
          images: ["pob-1.png", "pob-2.png", "pob-3.png"]
        },
        {
          title: "Guernica Club",
          link: "https://guernicaclub.com/",
          description:
            "A Project of Slicing Design to HTML, CSS and Javascript",
          status: "Deployed",
          tech: ["HTML", "CSS"],
          images: ["guernica-1.png", "guernica-2.png", "guernica-3.png"]
        },
        {
          title: "ST Man Hardware",
          link: "http://stmanhardware.com/",
          description:
            "A Project of Slicing Design to HTML, CSS and Javascript",
          status: "Deployed",
          tech: ["HTML", "CSS"],
          images: ["stman-1.png", "stman-2.png", "stman-3.png"]
        },
        {
          title: "UKM JuWAra",
          link: "https://ukmjuwara.id",
          description:
            "UKM JuWAra is a catalog for small businesses in Indonesia organised by ukmindonesia.id. The website is a digital catalog that used to add more exposure to all small businessess selected by UKM JuWAra, and it's running with Laravel Framework and jQuery.",
          status: "Deployed",
          tech: ["Laravel", "jQuery"],
          images: ["uj-1.jpg", "uj-2.jpg", "uj-3.jpg"]
        },
        {
          title: "Early Theory",
          link: "https://earlytheory.com",
          description:
            "Early Theory is an online service company that provides tarot services and also selling some of their stuff. This website has been developed in e-commerce type for tarot services. It took one month to finish this project, and I’m doing this project with one partner. My role for this project is as a front-end developer and also as UI/UX designer. For the back-end, we used Laravel. And for the javascript, we used jQuery.",
          status: "Deployed",
          tech: ["Laravel", "jQuery"],
          images: ["et1.jpg", "et2.jpg", "et3.jpg"]
        },
        {
          title: "So-Klin",
          link: "https://soklinlantai.com/",
          description:
            "So Klin is a fragrance product for floors and clothes. This website has been developed for company profiles and catalog products from the company. But there are no transactions or selling on the website. It linked to another website which is e-commerces. I'm doing this project by myself within two months. Furthermore, my role for this project is a full-stack developer. This website used WordPress for the back-end and used jQuery for javascript.",
          status: "Deployed",
          tech: ["Wordpress", "jQuery"],
          images: ["sk1.jpg", "sk2.jpg", "sk3.jpg"]
        },
        {
          title: "Burn Support Group",
          link: "http://burnsupport.id",
          description:
            "Burn Support Group is a community forum for burn survivors through education and training aimed at conducting social empowerment for burn survivors. This website has been developed for company profiles and campaigns from the company. There is a register page for candidates. I'm doing this project by myself within one month. Hence, my role for this project is a full-stack developer. This website used Laravel for the back-end and used jQuery for javascript. ",
          status: "Deployed",
          tech: ["Laravel", "jQuery"],
          images: ["bs1.jpg", "bs2.jpg", "bs3.jpg"]
        },
        {
          title: "Senimart",
          description:
            "Senimart is an alternative platform for art connoisseurs to find and buy works of art without having to come to an art gallery. Senimart is also intended as a forum for artists to interact with other new artists and open opportunities for collaboration between artists or their works with various artistic or non-art activations in an effort to introduce and develop the potential of artists and their works. This website has been developed in e-commerce type for selling any artworks. It needed four months to finish this project, and I’m doing this project with one partner. My role for this project is as a front-end developer and also as UI/UX designer. For the back-end, we used Laravel. And for the javascript, we used jQuery.",
          link: "https://senimart.id",
          status: "Deployed",
          tech: ["Laravel", "jQuery"],
          images: ["sm1.jpg", "sm2.jpg", "sm3.jpg", "sm4.jpg"]
        },
        {
          title: "Asia Stem Cell Center",
          description:
            "Asia Stem Cell Center is a stem cell laboratory that has an operational license certificate from the Ministry of Health where the processing and processing of stem cells are carried out with GMP standards. This website has been developed for company profiles. I'm doing this project by myself within two months. Moreover, my role for this project is a full-stack developer. This website used WordPress for the back-end.",
          link: "https://asiastemcellcenter.com",
          status: "Deployed",
          tech: ["Wordpress"],
          images: ["asc1.jpg", "asc2.jpg", "asc3.jpg"]
        }
      ]
    };
  }
};
</script>

<style scoped>
.col-md-6:nth-child(odd) {
  padding-right: 3rem;
}

.col-md-6:nth-child(even) {
  padding-left: 3rem;
}

.project {
  margin: auto;
  margin-bottom: 7rem;
  width: 80%;
  position: relative;
}

.project a:hover {
  color: #52a793;
  transition: 0.2s ease-in;
}

.project:after {
  width: 60%;
  height: 1px;
  content: "";
  background-color: #dddddd;
  position: absolute;
  bottom: -4rem;
  left: 50%;
  transform: translateX(-50%);
}

a:hover {
  text-decoration: none;
}

.info {
  align-items: center;
  margin-bottom: 0.5rem;
  display: flex;
}

.info h3 {
  font-weight: 700;
  margin: 0;
}

.css {
  color: #264de4;
}

.html {
  color: #d84924;
}

.satu {
  border-right: 2px solid #041e42;
  padding-right: 30px;
  margin-left: 0;
}

.title {
  align-items: center;
}

.title a {
  color: #384857;
  transition: all 0.2s ease-in;
}

.title a:hover {
  color: #52a793;
  transition: all 0.2s ease-in;
}

.logo {
  padding: 5px 10px;
  font-weight: bold;
  margin-left: 1rem;
  padding-right: 0;
  height: 34px;
  display: flex;
  align-items: center;
  font-size: 1.25rem;
}

.logo img {
  height: 20px;
  width: auto;
  padding-right: 0.5rem;
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
    margin-bottom: 0.5rem;
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
  color: #4783af;
}

p {
  margin-bottom: 0;
}
.laravel {
  color: #ff2d20;
}

.react {
  color: #222222;
}

.slick-next:before,
.slick-prev:before {
  color: #52a793 !important;
}

.status {
  border-radius: 30px;
  padding: 5px 10px;
  color: white;
  font-size: 0.85rem;
  position: absolute;
  top: 10px;
  right: 10px;
  z-index: 15;
  opacity: 0.9;
}

.green {
  background: #4cc62e;
}

.orange {
  background: #ecad4e;
}

.carousel-container {
  position: relative;
  border-radius: 1rem;
  box-shadow: 3px 3px 4px 4px rgba(0, 0, 0, 0.1);
}

.carousel-container img {
  object-fit: cover;
  border-radius: 1rem;
}

.slick-next {
  right: 20px;
}

.slick-prev {
  left: 20px;
  z-index: 20;
}

.slick-dots {
  bottom: -35px;
}
</style>
