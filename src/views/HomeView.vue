<template>
  <Navbar></Navbar>
  <Banner></Banner>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import Banner from "@/components/Banner.vue";

const getArticleInfo = async () => {
  await new Promise((resolve) => setTimeout(resolve, 3000));
  return true;
};

export default {
  name: "HomeView",
  components: {
    Navbar,
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
