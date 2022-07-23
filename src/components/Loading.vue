<template>
  <div id="loading-container">
    <img
      class="w-25 mx-auto"
      :src="require('../assets/img/astronaut-header.svg')"
      alt="moon"
    />
    <div class="rocket w-25 mx-auto">
      <img :src="require('../assets/img/rocket.svg')" alt="rocket" />
    </div>
  </div>
</template>
<script>
export default {
  name: "Loading",
};
</script>
