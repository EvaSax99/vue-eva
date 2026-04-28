<script setup lang="ts">
import { Card, CardContent } from "@/components/ui/card/";
import { computed, ref } from "vue";
import { Characters } from "./data";


// const listaSimpson = ref(Characters.slice(0, 6));

const inPagina = 6
const nuncPagina = ref(1)
const totalPaginae = (Math.ceil(Characters.length / inPagina))
const listaSimpson = computed(() => {
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
    class="flex flex-col items-center justify-center gap-8 w-full max-w-[1400px] my-8 mb-20"
  >
    <div class="text-center">
      <h1 class="font-bold text-xl lg:text-5xl mb-5">Simpsons Quote App</h1>
      <p class="mb-5">Click on the quote of your favorite Simpson character!</p>
    </div>
    <div class="grid grid-cols-2 md:grid-cols-3 gap-8 mx-auto">
      <Card
        v-for="character in listaSimpson"
        :key="character.id"
        class="cursor-pointer w-[220px] h-[240px] items-center text-center hover:bg-[#ee3133] hover:text-white transition-colors"
      >
        <CardContent class="flex flex-col items-center gap-1 w-full px-0">
          <img
            :src="`/imagines/simpsons/${character.imago}`"
            :alt="character.nomen"
            class="w-48 h-42 object-cover object-top mt-2 bg-[#ffde00] border border-black rounded-t-md"
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
          ? 'bg-yellow-200 text-yellow-600 cursor-not-allowed'
          : 'bg-[#ffde00] hover:bg-[#ee3133] hover:text-white'
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
           ? 'bg-[#ee3133] text-white'
           : 'bg-[#ffde00] hover:bg-[#ee3133] hover:text-white'
           ]"
        
      >
        {{ pagina }}
      </button>
      <!-- px-4 py-2 rounded-md font-medium transition-colors bg-[#ffde00] hover:bg-[#ee3133] hover:text-white -->

      <button
        :class="[
          'px-4 py-2 rounded-md font-medium transition-colors',
          nuncPagina === totalPaginae
          ? 'bg-yellow-200 text-yellow-600 cursor-not-allowed'
          : 'bg-[#ffde00] hover:bg-[#ee3133] hover:text-white'
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
