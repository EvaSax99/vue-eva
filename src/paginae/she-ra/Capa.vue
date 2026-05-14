<script setup lang="ts">

import { Button } from "@/components/ui/button";
import { RouterLink } from "vue-router";

</script>

<template>
  <div class="grid grid-rows-[auto_1fr_auto] min-h-screen">
    <header class="bg-[#d29ae4ee] w-full ]">
      <div
        class="flex flex-col md:flex-row justify-between items-center p-3 mx-auto max-w-[1400px ] md:px-20"
      >
      <div class="logo-container">
        <RouterLink to="/she-ra" active-class="hover:w-30">
          <img src="/imagines/she-ra/SheRa-logo.png" alt="Logo" class="w-[8rem] h-auto" />
        </RouterLink>
      </div>
        
        <div class="flex gap-6 pt-3 items-center">
          <RouterLink to="/she-ra/gallery" active-class="font-bold" class="text-[#8b349c] hover:text-white">
            Characters
          </RouterLink>
          <RouterLink to="/she-ra/about" active-class="font-bold" class="text-[#8b349c] hover:text-white">
            About
          </RouterLink>
          <Button
            variant="sherafont"
            size="elongatis"
            class="bg-[#8b349c] text-white  border-radius:50 border-[#d29ae4ee] hover:bg-white focus:bg-white hover:text-[#8b349c] "
          >
            <RouterLink to="/she-ra"> Exit </RouterLink>
          </Button>
        </div>
      </div>

     
    </header>
    <main class="mb-20 mt-10">
      <RouterView />
    </main>

    <footer class="bg-[#d29ae4ee] text-center justify-center items-center pb-5">

      <div class="mt-5 text-[#8b349c]">
        <strong>All Rights Reserved</strong>
        <p>Creadores Originales: Larry DiTillio y J. Michael Straczynski -1985-</p> 
        <p>Creador de la serie moderna: ND Stevenson -2018-</p>
      </div>

      <small class="mb-10 text-[#8b349c]"> This app was done by Eva Clement </small>
    </footer>
  </div>
</template>

<style scoped>
.RouterLink {
  color: #8b349c;

}
.logo-container {
  height: 70px;
  width: 150px;
  display: flex;
  background-color: white;
  border-radius: 30px;
  justify-content: center;
  align-items: center;

}

</style>
