<script lang="ts" setup>
import { Button } from "@/components/ui/button";


import {
  Dialog,
  DialogContent,
  DialogDescription,
  DialogHeader,
  DialogTitle,
  DialogTrigger,
} from "@/components/ui/dialog";
import { Input } from "@/components/ui/input";
import { useRouter } from "vue-router";
import { ref } from "vue";

const dialogApertaEst = ref<boolean>(false)
const quaestio = ref<string>('')

const router = useRouter()

const cumKeyPressumEnter = (eventus: KeyboardEvent) => {
  if (eventus.key === 'Enter') {
    const textusItinerans = quaestio.value.trim()
    if (textusItinerans.length > 0 && textusItinerans.endsWith('?')){
      dialogApertaEst.value = false

      router.push({
        path: '/indecision',
        state: { quaestio: textusItinerans}
      })

      quaestio.value = ''

    }
  }

}

</script>

<template>
  <div
    class="bg-[rgb(21,25,52)] h-screen text-white font-sans text-center flex flex-col items-center justify-center gap-12 w-screen fixed"
  >
    <img
      class="absolute opacity-20"
      src="/imagines/batman/tonitrui.png"
      alt="Batman"
    />
    <h1
      class="text-5xl md:text-7xl lg:text-8xl font-bold pb-5 md:pb-20 z-10 transition-all"
    >
      <span class="text-[rgb(24,188,246)]">Diseños</span> Web y
      <br />
      Apps <span class="text-[rgb(24,188,246)]">Interactivas</span>
    </h1>

    <p class="text-lg md:text-2xl transition-all">
      Aprendiendo a crear aplicaciones web
    </p>
    <div class="z-10">
      <Dialog
      :open="dialogApertaEst"
      @update:open="dialogApertaEst = $event"
      >
        <DialogTrigger as-child>
          <Button
            variant="default"
            class="mr-2 bg-[rgb(24,188,246)] md-py-5 md:px-6 md:text-lg hover:bg-[rgb(30,111,141)] hover:text-white transition-all]"
          >
            Sí o No
          </Button>
        </DialogTrigger>
        <DialogContent class="sm:max-w-[425px] bg-[rgb(21,25,52)] text-white  border-[rgb(24,182,246)] ">
          <DialogHeader>
            <DialogTitle class="text-white">Pregúntame</DialogTitle>
            <DialogDescription class="text-gray-300">
              No sigas con tus dudas, yo te responderé SÍ o NO
            </DialogDescription>
          </DialogHeader>
          <div class="mt-4">
            <Input
             placeholder="Escribe tu pregunta aquí..." 
             class="bg-[rgb(31,35,62)] text-white placeholder:text-gray-400 border-[rgb(24,182,246)]"
             v-model="quaestio"
             @keydown="cumKeyPressumEnter"
             />
          </div>

        </DialogContent>
      </Dialog>

      <Button
        variant="default"
        class="mr-2 bg-[rgb(24,188,246)] md-py-5 md:px-6 md:text-lg hover:bg-[rgb(30,111,141)] hover:text-white transition-all]"
      >
        <router-link to="/batman">Batman</router-link>
      </Button>
      <Button
        variant="default"
        class="mr-2 bg-[rgb(24,188,246)] md-py-5 md:px-6 md:text-lg hover:bg-[rgb(30,111,141)] hover:text-white transition-all]"
      >
        <router-link to="/simpsons">Simpsons</router-link>
      </Button>
      <Button
        variant="default"
        class="mr-2 bg-[rgb(24,188,246)] md-py-5 md:px-6 md:text-lg hover:bg-[rgb(30,111,141)] hover:text-white transition-all]"
      >
        <a href="https://www.upv.es">UPV</a>
      </Button>
    </div>
  </div>
</template>
<style scoped></style>
