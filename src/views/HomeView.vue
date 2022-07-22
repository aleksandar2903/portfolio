<template>
  <Navbar></Navbar>
  <Banner></Banner>
  <Skills></Skills>
  <Projects></Projects>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import Banner from "@/components/Banner.vue";
import Skills from "@/components/Skills.vue";
import Projects from "@/components/Projects.vue";

const getArticleInfo = async () => {
  await new Promise((resolve) => setTimeout(resolve, 100));
  return true;
};

export default {
  name: "HomeView",
  components: {
    Navbar,
    Banner,
    Skills,
    Projects,
  },
  async setup() {
    const article = await getArticleInfo();
    return {
      article,
    };
  },
};
</script>
