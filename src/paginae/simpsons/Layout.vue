<script setup lang="ts">
import LogoSimpsons from "@/components/LogoSimpsons.vue";
import { Button } from "@/components/ui/button";
import { RouterLink } from "vue-router";
</script>

<template>
  <div class="grid grid-rows-[auto_1fr_auto] min-h-screen">
    <header class="bg-[#ffde00] w-full border border-black">
      <div
        class="flex flex-col md:flex-row justify-between items-center p-3 mx-auto max-w-[1400px ] md:px-20"
      >
        <LogoSimpsons estilus="w-[8rem] h-auto" />
        <div class="flex gap-6 pt-3">
          <RouterLink to="/simpsons/gallery" active-class="font-bold">
            Characters
          </RouterLink>
          <RouterLink to="/simpsons/about" active-class="font-bold">
            About
          </RouterLink>
          <Button
            variant="tertiarius"
            side="elongatis"
            class="bg-[#ee3133] hover:bg-[#ffde00] hover:border border-black focus:bg-[#ffde00]"
          >
            <RouterLink to="/simpsons"> Exit </RouterLink>
          </Button>
        </div>
      </div>

     
    </header>
    <main>
      <RouterView />
    </main>

    <footer class="bg-[#ffde00] text-center items-center justify-center border border-black ">

      <div class="mt-5">
        <strong>All Rights Reserved</strong> - Oh Lord Matt Groening - 1989-2023
      </div>

      <small class="mb-5"> This app was done by Eva Clement </small>
    </footer>
  </div>
</template>

<style scoped></style>
