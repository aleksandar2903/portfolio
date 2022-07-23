<template>
  <section class="py-5 px-md-0 text-black" id="project">
    <div class="container">
      <div class="row">
        <div class="col-12">
          <h1 class="title mt-5">Projects</h1>
          <p class="w-75 mx-auto text-center h5 my-4">
            I love to learn new things and experiment with new technologies.
            These are some of the major languages, tehnologies, tools and
            platforms I have worked with:
          </p>
          <div class="row mt-5 px-md-3 gx-0 mx-auto w-75">
            <div class="col-4">
              <button
                @click.prevent="getWebProjects"
                :class="active === 'webProjects' ? 'bg-black text-white' : ''"
                class="button-transition-dark px-0 text-center w-100"
              >
                <h6>Web</h6>
              </button>
            </div>
            <div class="col-4">
              <button
                @click.prevent="getDesktopProjects"
                :class="
                  active === 'desktopProjects' ? 'bg-black text-white' : ''
                "
                class="button-transition-dark px-0 text-center w-100"
              >
                <h6>Desktop</h6>
              </button>
            </div>
            <div class="col-4">
              <button
                @click.prevent="getMobileProjects"
                :class="
                  active === 'mobileProjects' ? 'bg-black text-white' : ''
                "
                class="button-transition-dark px-0 text-center w-100"
              >
                <h6>Mobile</h6>
              </button>
            </div>
          </div>
          <div class="row mt-5">
            <div
              class="col-md-6 col-xl-4"
              v-for="(project, index) in projects"
              :key="index"
            >
              <div class="proj-imgbx">
                <img :src="require('../assets/img/' + project.images[0])" />
                <div class="proj-txtx px-4">
                  <h3>{{ project.title }}</h3>
                  <span>{{ project.tehnologies }}</span>
                  <div class="row gap-4 mt-3">
                    <div>
                      <button
                        @click="showGallery(index)"
                        class="btn rounded-0 btn-outline-dark"
                      >
                        Show gallery
                      </button>
                    </div>
                    <div v-if="project.github">
                      <a
                        class="btn btn-link text-black"
                        :href="project.github"
                        target="_blank"
                        >Source code</a
                      >
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
  <Gallery v-if="show" @close="show = false" :images="images"></Gallery>
</template>
<script>
import Gallery from "./Gallery.vue";
const webProjects = [
  {
    id: 1,
    title: "Inventory Management System",
    tehnologies: "PHP, Laravel, Vue, Bootstrap",
    github: "https://github.com/aleksandar2903/IMS_Laravel_Vue",
    description: "",
    images: [
      "ims_web1.png",
      "ims_web2.png",
      "ims_web3.png",
      "ims_web4.png",
      "ims_web5.png",
      "ims_web6.png",
      "ims_web7.png",
      "ims_web9.png",
      "ims_web10.png",
      "ims_web11.png",
      "ims_web12.png",
      "ims_web13.png",
    ],
  },
  {
    id: 2,
    title: "Movie App (TMDB API)",
    tehnologies: "PHP, Laravel, Bootstrap",
    github: "",
    description: "",
    images: [
      "movieapp1.png",
      "movieapp2.png",
      "movieapp3.png",
      "movieapp4.png",
    ],
  },
  {
    id: 3,
    title: "Reddit Clone",
    tehnologies: "PHP, Laravel, Vue, Bootstrap",
    github: "",
    description: "",
    images: [
      "reddit1.png",
      "reddit2.png",
      "reddit3.png",
      "reddit4.png",
      "reddit5.png",
      "reddit6.png",
      "reddit7.png",
      "reddit8.png",
      "reddit9.png",
    ],
  },
  {
    id: 4,
    title: "Rent a Car",
    tehnologies: "PHP, Laravel, Bootstrap",
    github: "",
    description: "",
    images: [
      "rentacar1.png",
      "rentacar2.png",
      "rentacar3.png",
      "rentacar4.png",
      "rentacar5.png",
    ],
  },
];
const desktopProjects = [
  {
    id: 1,
    title: "e-Cafe",
    tehnologies: "C#, UWP, SQLite",
    github: "",
    description: "",
    images: [
      "ecafe1.png",
      "ecafe2.png",
      "ecafe3.png",
      "ecafe4.png",
      "ecafe5.png",
      "ecafe6.png",
    ],
  },
  {
    id: 2,
    title: "Inventory Management System",
    tehnologies: "C#, Windows Forms, SQL Server",
    github: "https://github.com/aleksandar2903/Inventory-Managment-System",
    description: "",
    images: [
      "ims1.png",
      "ims2.png",
      "ims3.png",
      "ims4.png",
      "ims5.png",
      "ims6.png",
    ],
  },
];
const mobileProjects = [
  {
    id: 1,
    title: "Movie App (TMDB API)",
    tehnologies: "C#, Xamarin, TMDB API",
    github: "",
    description: "",
    images: [
      "movie1.png",
      "movie2.png",
      "movie3.png",
      "movie4.png",
      "movie5.png",
      "movie6.png",
    ],
  },
  {
    id: 2,
    title: "Recipes App (Tasty API)",
    tehnologies: "C#, Xamarin, Tasty API",
    github: "",
    description: "",
    images: [
      "recipeapp1.png",
      "recipeapp2.png",
      "recipeapp3.png",
      "recipeapp4.png",
      "recipeapp5.png",
      "recipeapp6.png",
    ],
  },
  {
    id: 3,
    title: "Smart Shop",
    tehnologies: "C#, Xamarin, Smart Shop API (Web API - ASP.NET Core)",
    github: "",
    description: "",
    images: [
      "mss1.png",
      "mss2.jpg",
      "mss3.jpg",
      "mss4.jpg",
      "mss5.jpg",
      "mss6.jpg",
    ],
  },
];
export default {
  name: "Projects",
  data() {
    return {
      images: [],
      projects: [],
      show: false,
      active: "webProjects",
    };
  },
  mounted() {
    this.getWebProjects();
  },
  methods: {
    showGallery(index) {
      this.images = this.projects[index].images;
      this.show = true;
    },
    getWebProjects() {
      this.projects = webProjects;
      this.active = "webProjects";
    },
    getDesktopProjects() {
      this.projects = desktopProjects;
      this.images = this.projects[0].images;
      this.active = "desktopProjects";
    },
    getMobileProjects() {
      this.projects = mobileProjects;
      this.active = "mobileProjects";
    },
  },
  components: { Gallery },
};
</script>
