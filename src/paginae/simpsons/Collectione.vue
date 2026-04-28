<script setup lang="ts">
import { Card, CardContent } from "@/components/ui/card/";
import { ref } from "vue";
import { Characters } from "./data";

const listaSimpson = ref(Characters.slice(0, 6));
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
  </div>
</template>

<style scoped></style>
