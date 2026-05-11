<script setup lang="ts">
import { Card, CardContent } from "@/components/ui/card/";
import { computed, ref } from "vue";
import { Characters } from "./data";
import { useRouter } from "vue-router";


// const listaSimpson = ref(Characters.slice(0, 6));
const router = useRouter()
const inPagina = 6
const nuncPagina = ref(1)
const totalPaginae = (Math.ceil(Characters.length / inPagina))
const listaSheRa = computed(() => {
    const inicio = (nuncPagina.value - 1) * inPagina;
    const fin = inicio + inPagina;
    return Characters.slice(inicio, fin);
});

const ireAdPaginam = (pagina:number) => {
    if (pagina >= 1 && pagina <= totalPaginae) {
        nuncPagina.value = pagina;
    }
}

const paginaNumeri: number[] =[...Array(totalPaginae)].map((_, i) => i + 1)


</script>

<template>
  <div
    class="flex flex-col items-center justify-center gap-8 w-full max-w-[1400px] my-8 mx-auto"
  >
    <div class="text-center">
      <h1 class="font-bold text-xl lg:text-5xl mb-5 text-[#8b349c]">She-Ra Quote App</h1>
      <p class="mb-5">Click on the quote of your favorite She-Ra character!</p>
    </div>
    <div class="grid grid-cols-2 md:grid-cols-3 gap-8 mx-auto">
      <Card
        v-for="character in listaSheRa"
        :key="character.id"
        class="cursor-pointer w-[220px] h-[240px] items-center text-center hover:bg-[#b11a83ee] hover:text-white transition-colors"
      >
        <CardContent
         class="flex flex-col items-center gap-1 w-full px-0"
        @click = "router.push(`/she-ra/gallery/${character.id}`)"
        >
          <img
            :src="`/imagines/she-ra/${character.imago}`"
            :alt="character.nomen"
            class="w-48 h-42 object-cover object-top mt-2 bg-white border border-black rounded-t-md"
          />
          <h2>{{ character.nomen }}</h2>
        </CardContent>
      </Card>
    </div>
    <!-- px-4 py-2 rounded-md font-medium transition-colors bg-[#ffde00] hover:bg-[#ee3133] hover:text-white -->
    <div class="flex items-center justify-center gap-2 mt-4">
      <button
        :class="[
          'px-4 py-2 rounded-md font-medium transition-colors',
          nuncPagina === 1
          ? 'bg-[#edccf8ee] text-[#8b349c] cursor-not-allowed'
          : 'bg-[#d29ae4ee] hover:bg-[#b11a83ee] hover:text-white'
        ]"
        @click="ireAdPaginam(nuncPagina - 1)"
        :disabled="nuncPagina === 1"
      >
        Anterior
      </button>

      <button
        v-for="pagina in paginaNumeri"
        :key="pagina"
        @click="ireAdPaginam(pagina)"
        :class="[
          'w-10 h-10 rounded-md font-medium transition-colors',
           nuncPagina === pagina 
           ? 'bg-[#b11a83ee] text-white'
           : 'bg-[#d29ae4ee] hover:bg-[#8b349c] hover:text-white'
           ]"
        
      >
        {{ pagina }}
      </button>
      <!-- px-4 py-2 rounded-md font-medium transition-colors bg-[#ffde00] hover:bg-[#ee3133] hover:text-white -->

      <button
        :class="[
          'px-4 py-2 rounded-md font-medium transition-colors',
          nuncPagina === totalPaginae
          ? 'bg-[#edccf8ee] text-[#8b349c] cursor-not-allowed'
          : 'bg-[#d29ae4ee] hover:bg-[#b11a83ee] hover:text-white'
        ]"
        @click="ireAdPaginam(nuncPagina + 1)"
        :disabled="nuncPagina === totalPaginae"
      >
        Siguiente
      </button>
    </div>
  </div>
</template>

<style scoped></style>
