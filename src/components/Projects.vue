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
            <div class="col-4" v-for="project in projects" :key="project.id">
              <div class="proj-imgbx">
                <img :src="require('../assets/img/' + project.images[0])" />
                <div class="proj-txtx">
                  <h4>{{ project.title }}</h4>
                  <span>{{ project.tehnologies }}</span>
                  <div class="proj-git">
                    <a href="{linkGit}" target="_blank"
                      ><img
                        src="../assets/img/imgProjectFisiotherapp.png"
                        alt="Github"
                    /></a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
const webProjects = [
  {
    id: 1,
    title: "Inventory Management System",
    tehnologies: "Laravel, Vue, Bootstrap",
    github: "",
    description: "",
  },
  {
    id: 2,
    title: "Movie App (TMDB API)",
    tehnologies: "Laravel, Bootstrap",
    github: "",
    description: "",
  },
  {
    id: 3,
    title: "Reddit Clone",
    tehnologies: "Laravel, Vue, Bootstrap",
    github: "",
    description: "",
  },
];
const desktopProjects = [
  {
    id: 1,
    title: "e-Cafe",
    tehnologies: "UWP, C#, SQLite",
    github: "",
    description: "",
    images: [
      "eCafe_img1.png",
      "eCafe_img2.png",
      "eCafe_img3.png",
      "eCafe_img4.png",
      "eCafe_img5.png",
      "eCafe_img6.png",
    ],
  },
];
const mobileProjects = [
  {
    name: "Visual Studio",
    level: "90",
  },
];
export default {
  name: "Skills",
  data() {
    return {
      projects: [],
      active: "webProjects",
    };
  },
  mounted() {
    this.getDesktopProjects();
  },
  methods: {
    getWebProjects() {
      this.projects = webProjects;
      this.active = "webProjects";
    },
    getDesktopProjects() {
      this.projects = desktopProjects;
      this.active = "desktopProjects";
    },
    getMobileProjects() {
      this.projects = mobileProjects;
      this.active = "mobileProjects";
    },
  },
};
</script>
