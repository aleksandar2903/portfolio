<template>
  <Navbar></Navbar>
  <Banner></Banner>
  <Skills></Skills>
  <Projects></Projects>
  <Contact></Contact>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import Skills from "@/components/Skills.vue";
import Projects from "@/components/Projects.vue";
import Contact from "@/components/Contact.vue";
import Banner from "../components/Banner.vue";

const getArticleInfo = async () => {
  await new Promise((resolve) => setTimeout(resolve, 2000));
  return true;
};

export default {
  name: "HomeView",
  components: {
    Navbar,
    Skills,
    Projects,
    Contact,
    Banner,
  },
  async setup() {
    const article = await getArticleInfo();
    return {
      article,
    };
  },
};
</script>
