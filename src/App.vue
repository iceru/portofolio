<template>
  <div id="app">
    <div>
      <div class="container">
        <nav class="d-flex justify-content-center">
          <div class="navigations py-3">
            <router-link
              to="/projects"
              active-class="active"
              class="px-4 px-lg-5"
              >Projects</router-link
            >
            <router-link to="/" active-class="active" class="animation px-3">
              <img src="@/assets/logo.png" alt=""
            /></router-link>
            <router-link
              to="/contact"
              active-class="active"
              class="px-4 px-lg-5"
              >Contact</router-link
            >
          </div>
        </nav>
        <transition name="fade" mode="out-in">
          <router-view />
        </transition>
        <footer class="d-flex">
          <div class="social">
            <a href="https://www.linkedin.com/in/hafizeto/" target="_blank"
              ><i
                class="fab fa-linkedin-in fa-2x mr-2 purple"
                aria-hidden="true"
              ></i
            ></a>
            <a
              href="https://github.com/iceru"
              target="_blank"
              rel="noopener noreferrer"
              ><i class="fab fa-github fa-2x mr-2 purple" aria-hidden="true"></i
            ></a>
            <a
              href="https://twitter.com/Hafizeto"
              target="_blank"
              rel="noopener noreferrer"
              ><i class="fab fa-twitter fa-2x purple"></i
            ></a>
          </div>
          <div class="copyright">
            Copyright <i class="fas fa-copyright"></i> - Hafiz
            {{ new Date().getFullYear() }}
          </div>
        </footer>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App"
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700&display=swap");
#app {
  font-family: "Cairo", sans-serif;
  width: 100vw;
  overflow: hidden;
}

a:hover {
  text-decoration: none !important;
}

.container {
  background-color: white;
  padding: 2rem 8px !important;
}

body {
  overflow-x: hidden;
  color: #384857;
}

.navigations img {
  width: 60px;
}

.navigations a {
  color: #384857;
  transition: all 0.2s ease-in;
  font-weight: 600;
  font-size: 1.1rem;
}

.slick-next:before,
.slick-prev:before {
  color: #52a793 !important;
}

.navigations a:hover {
  color: #52a793;
  transition: all 0.2s ease-in;
}

.purple {
  color: #52a793;
  font-weight: 600;
}

footer {
  padding: 20px 5%;
  justify-content: space-between;
  align-items: baseline;
}

.navigations .active {
  font-weight: 700;
  color: #52a793;
}

.animation img {
  transition: 0.2s ease-in-out;
}

.animation img:hover {
  transform: scale(1.2);
  transition: 0.2s ease-in-out;
}

.fade-enter,
fade-leave-to {
  opacity: 0;
  transform: translateX(2em);
}

.fade-enter-active,
.fade-leave-active {
  transition: all 0.3s ease;
}

p {
  margin-bottom: 0 !important;
}

@media only screen and (max-width: 1300px) {
  footer {
    padding: 20px 5%;
    justify-content: space-between;
  }
}
</style>
