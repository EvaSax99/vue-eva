<script lang="ts" setup>
import { RouterLink } from "vue-router";
import { Button } from "@/components/ui/button";
import CarrusShera from "@/components/ui/CarrusShera.vue";
import { MapPin, Phone, Mail, Instagram, Linkedin, MessageCircle, X, } from "lucide-vue-next";

const photos = [
  "adora",
  "catra",
  "glimmer",
  "bow",
  "entrapta",
  "mermista",
  "sea-hawk",
  "scorpia",
  "horde-prime",
  "nectossa",
  "angella",
  "castaspella",
  "swift-wind",
  "lonnie",
  "double-trouble",
  "shadow-weaver",
  "frosta",
  "razz",
  "spinnerella",
  "perfuma",
  "hordak",
  "light-hope",
  "rogelio",
  

];
</script>

<template>
	<div class="flex flex-row  justify-end sm:justify-end gap-5 sm:gap-5 mr-10 mt-8">
      <Button
        variant="sherafont"
        size="elongatis"
        class="text-[#8b349c] border-[#8b349c] hover:bg-[#d29ae4ee] hover:text-white hover:border-[#8b349c]"
      >
        <RouterLink to="/">Exit</RouterLink>
      </Button>
      <Button
        variant="sherafont"
        size="elongatis"
        class="text-[#8b349c] border-[#8b349c] hover:bg-[#d29ae4ee] hover:text-white hover:border-[#8b349c]"
      >
        <RouterLink to="/she-ra/about">Enter</RouterLink>
      </Button>
    </div>
  <div
    class="bg-[#fff] min-h-screen text-center p-4 flex flex-col items-center justify-center "
  >
    <img
      src="/imagines/she-ra/SheRa-logo.png"
      alt="She-Ra Logo"
      class="pb-10"
    />
    <h1 class="text-xl my-1 font-medium text-[#580968] mt-20 ">
      Discover some of the most amazing Quotes from She-Ra and the Princesses of
      Power
    </h1>
    <div>
      <strong class="text-[#580968] mb-20"
        >This is an unofficial app (even though it looks so cool!)</strong
      >
    </div>
    
    <div class="flex gap-12 mt-8 mb-20">
      <img
        class="object-contain hidden md:block"
        src="/imagines/she-ra/adora.png"
        alt="Adora"
        width="250px"
      />
      <img
        class="object-contain hidden md:block mt-20"
        src="/imagines/she-ra/catra.png"
        alt="Catra"
        width="400px"
      />
      <img
        class="object-contain hidden md:block mt-0"
        src="/imagines/she-ra/glimmer.png"
        alt="Glimmer"
        width="200px"
      />
    </div>
	 

	<section
      id="videre"
      class=""
    >
	 <div class="contenedor-texto"> 
        <h2 class="text-md md:text-lg lg:text-xl text-[#580968] font-medium mt-20 mb-0">
            Algunas imágenes de los personajes de She-Ra y las princesas del poder
        </h2>
    </div>
	<div class="w-full flex items-center justify-center min-h-[40vh] lg:min-h-[70vh] mb-20">
		<CarrusShera
        :photos="photos"
        basePath="/imagines/she-ra"
        :autoPlayDelay="4000"
      />

	</div>
      
    </section>
  </div>
  <footer class="w-full bg-[#580968] text-white py-12">
      <div
        class="flex flex-col md:flex-row md:justify-around gap-8 max-w-3xl mx-auto"
      >
        <div class="space-y-4 text-center md:text-left">
          <h3 class="text-xl font-bold text-white">Información de Contacto</h3>

          <div class="space-y-2">
            <p class="flex items-center gap-2 justify-center md:justify-start">
              <Phone class="w-5 h-5"/>
              +1 (555) 123-4567
            </p>
            <p class="flex items-center gap-2 justify-center md:justify-start">
              <Mail class="w-5 h-5"/>
              shera-moreAdora@she-ra.com
            </p>
            <p class="flex items-center gap-2 justify-center md:justify-start">
              <MapPin class="w-5 h-5"/>
               The Fright Zone, Etheria
            </p>
          </div>
        </div>

        
        <div class="space-y-4 text-center md:text-left text-white ">
          <h3 class="text-xl font-bold text-white">Síguenos</h3>
          <div class="flex gap-8 justify-center">
            <X class="w-10 h-10"/>
            <Instagram class="w-10 h-10"/>
            <Linkedin class="w-10 h-10"/>
            <MessageCircle class="w-10 h-10"/>
          </div>
        </div>
      </div>
    </footer>
</template>

<style scoped>
/* .contenedor-texto {
	width: 100%;
	height: 20px;
	display: flex;
	justify-content: center;
	align-items:center;
	background-color: #580968;
	color: white;

} */

</style>
