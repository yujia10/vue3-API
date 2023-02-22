<script setup>
import CardsSuspense from "./components/CardsSuspense.vue";
import RickMorty from "./components/RickMorty.vue"
import Hero from "./components/Hero.vue"

import { ref } from "vue"

const isThrones = ref(true)
</script>

<template>
  <main>
    <Hero :isThrones="isThrones" @selectShow="isThrones = !isThrones" />


    <!-- <CardsSuspense v-if="isThrones"/>
    <RickMorty v-else/> -->

    <!-- keepAlive:a build-in component to manage state -->
    <KeepAlive>
      <Component :is="isThrones ? CardsSuspense : RickMorty" />
    </KeepAlive>

  </main>
</template>
