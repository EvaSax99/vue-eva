<script lang="ts" setup>
import { Button } from "@/components/ui/button";
</script>

<template>
  <div
    class="bg-[rgb(21,25,52)] h-screen text-white font-sans text-center flex flex-col items-center justify-center gap-12 w-screen fixed"
  >
  <img class="absolute opacity-20" src="/imagines/batman/tonitrui.png" alt="Batman">
    <h1 class="text-5xl md:text-7xl lg:text-8xl font-bold pb-5 md:pb-20 z-10 transition-all">
      <span class="text-[rgb(24,188,246)]">Diseños</span> Web y
      <br />
       Apps <span class="text-[rgb(24,188,246)]">Interactivas</span>
    </h1>

    <p class="text-lg md:text-2xl transition-all">
        Aprendiendo a crear aplicaciones web
    </p>
    <div class="z-10">
      <Button variant="default" class="mr-2 bg-[rgb(24,188,246)] md-py-5 md:px-6 md:text-lg hover:bg-[rgb(30,111,141)] hover:text-white transition-all]">
        <router-link to="/indecision">Sí o No</router-link>
      </Button>
      <Button variant="default" class="mr-2 bg-[rgb(24,188,246)] md-py-5 md:px-6 md:text-lg hover:bg-[rgb(30,111,141)] hover:text-white transition-all]">
        <router-link to="/batman">Batman</router-link>
      </Button>
      <Button variant="default" class="mr-2 bg-[rgb(24,188,246)] md-py-5 md:px-6 md:text-lg hover:bg-[rgb(30,111,141)] hover:text-white transition-all]">
        <router-link to="/simpsons">Simpsons</router-link>
      </Button>
      <Button variant="default" class="mr-2 bg-[rgb(24,188,246)] md-py-5 md:px-6 md:text-lg hover:bg-[rgb(30,111,141)] hover:text-white transition-all]">
        <a href="https://www.upv.es">UPV</a>
      </Button>
    </div>
  </div>
</template>
<style scoped></style>
