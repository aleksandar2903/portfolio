<template>
  <section class="px-2 py-5 px-md-0 bg-black" id="skills">
    <div class="container mb-5">
      <div class="row">
        <div class="col-12">
          <h1 class="title mt-5">Skills</h1>
          <p class="w-75 mx-auto text-center h5 my-4">
            I love to learn new things and experiment with new technologies.
            These are some of the major languages, tehnologies, tools and
            platforms I have worked with:
          </p>
          <div class="row mt-5">
            <div class="col-md-5 col-xl-3">
              <div class="row gap-2 px-3 px-md-0">
                <button
                  @click.prevent="getLanguages"
                  :class="active === 'languages' ? 'bg-light text-black' : ''"
                  class="text-start py-3 button-transition"
                >
                  <h4>Languages & Databases</h4>
                  <p>Programming languages that I prefer to use the most</p>
                </button>
                <button
                  @click.prevent="getFrameworks"
                  :class="active === 'frameworks' ? 'bg-light text-black' : ''"
                  class="text-start py-3 button-transition"
                >
                  <h4>Frameworks & Tehnologies</h4>
                  <p>Frameworks and tehnologies that I use the most</p>
                </button>
                <button
                  @click.prevent="getTools"
                  :class="active === 'tools' ? 'bg-light text-black' : ''"
                  class="text-start py-3 button-transition"
                >
                  <h4>Tools & Platforms</h4>
                  <p>My favourite tools and platforms</p>
                </button>
              </div>
            </div>
            <div class="col-md-7 col-xl-9 ps-md-5 mt-4 mt-lg-0">
              <div class="row" v-for="skill in skills" :key="skill.name">
                <div class="mb-4">
                  <h5>{{ skill.name }}</h5>
                  <div class="progress bg-dark" style="height: 10px">
                    <div
                      class="progress-bar progress-bar-striped bg-light"
                      role="progressbar"
                      aria-label="Danger example"
                      :style="{ width: skill.level + '%' }"
                      aria-valuenow="100"
                      aria-valuemin="0"
                      aria-valuemax="100"
                    ></div>
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
const languages = [
  {
    name: "C#",
    level: "70",
  },
  {
    name: "PHP",
    level: "50",
  },
  {
    name: "Javascript",
    level: "55",
  },
  {
    name: "Microsoft SQL Server",
    level: "65",
  },
  {
    name: "MySQL",
    level: "50",
  },
];
const frameworks = [
  {
    name: "ASP.NET Core",
    level: "70",
  },
  {
    name: "Laravel",
    level: "70",
  },
  {
    name: "Xamarin",
    level: "75",
  },
  {
    name: "Vue.js",
    level: "65",
  },
  {
    name: "Bootstrap",
    level: "85",
  },
];
const tools = [
  {
    name: "Visual Studio",
    level: "90",
  },
  {
    name: "Visual Studio Code",
    level: "90",
  },
  {
    name: "Git",
    level: "55",
  },
  {
    name: "Github",
    level: "55",
  },
  {
    name: "Postman",
    level: "80",
  },
];
export default {
  name: "Skills",
  data() {
    return {
      skills: [],
      active: "languages",
    };
  },
  mounted() {
    this.getLanguages();
  },
  methods: {
    getLanguages() {
      this.skills = languages;
      this.active = "languages";
    },
    getFrameworks() {
      this.skills = frameworks;
      this.active = "frameworks";
    },
    getTools() {
      this.skills = tools;
      this.active = "tools";
    },
  },
};
</script>
