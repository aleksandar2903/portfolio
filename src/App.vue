<template>
  <Suspense>
    <template #default>
      <Home></Home>
    </template>
    <template #fallback>
      <Loading></Loading>
    </template>
  </Suspense>
</template>

<script setup>
import { defineAsyncComponent } from "vue";
import Loading from "@/components/Loading.vue";
import Home from "@/views/HomeView.vue";
</script>
