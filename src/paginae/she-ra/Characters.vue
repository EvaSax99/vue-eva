<script setup lang="ts">
import { ref, watch } from "vue";
import { computed } from "vue";

import { useRoute, useRouter} from "vue-router";
import { Characters, type Character } from "./data";
import { CheckIcon, ChevronsUpDownIcon } from 'lucide-vue-next'
import { Button } from '@/components/ui/button'
import { cn } from '@/lib/utils'
import {
  Command,
  CommandEmpty,
  CommandGroup,
  CommandInput,
  CommandItem,
  CommandList,
} from '@/components/ui/command'
import {
  Popover,
  PopoverContent,
  PopoverTrigger,
} from '@/components/ui/popover'
// import SelectLabel from "@/components/ui/select/SelectLabel.vue";

const route = useRoute()
const router = useRouter()

const character = ref<Character | undefined>(
    Characters.find( char => char.id === Number(route.params.id))
)

const sheRaOptions = Characters.map( char => ({
  value: char.id.toString(),
  label: char.nomen

}))

const open = ref(false)
const value = ref(route.params.id?.toString() || "")

watch(() => route.params.id, (newId) => {
  character.value = Characters.find( char => char.id === Number(newId))
  value.value = newId?.toString() || ''
})

const selectCharacter = (characterId: string) => {
  value.value = characterId 
  open.value = false
  router.push(`/she-ra/gallery/${characterId}`)
}

const selectedLabel = computed (() => {
  if (!value.value) return 'Selecciona un personaje...'
  return sheRaOptions.find(option => option.value === value.value)?.label || 'Selecciona un personaje...'
  })


</script>

<template>
  <div
  v-if="character"
  class="w-full md: mx-auto my-10 mb-10 px-5 md:px-20"
  >
    <div class="mb-8">
      <label class="block text-lg font-semibold mb-2 text-[#3a0c43]">Buscar personaje:</label>
  <Popover v-model:open="open">
    <PopoverTrigger as-child>
      <Button
        variant="outline"
        role="combobox"
        :aria-expanded="open"
        class="w-[200px] justify-between bg-[#8b349c] hover:bg-[#d29ae4ee] border-2 border-[#8b349c] font-semibold text-white"
      >
        {{ selectedLabel }}
        <ChevronsUpDownIcon class="ml-2 h-4 w-4 shrink-0 opacity-50" />
      </Button>
    </PopoverTrigger>
    <PopoverContent class="w-[200px] p-0 border-2 border-[#8b349c] bg-white">
      <Command>
        <CommandInput class="border-b-2 border-[#e7b9f0]" placeholder="Buscar..." />
        <CommandList>
          <CommandEmpty>No se encontró</CommandEmpty>
          <CommandGroup>
            <CommandItem
              v-for="option in sheRaOptions"
              :key="option.value"
              :value="option.value"
              @select="selectCharacter(option.value)"
              class="hover:bg-[#d29ae4ee] hover:text-white cursor-pointer font-medium transition-colors"
            >
              {{ option.label }}
              <CheckIcon
                :class="cn(
                  'ml-auto',
                   value === option.value ? 'opacity-100' : 'opacity-0',
                )"
              />
            </CommandItem>
          </CommandGroup>
        </CommandList>
      </Command>
    </PopoverContent>
  </Popover>


 </div> 


  <div 
  class="flex flex-col lg:flex-row lg:justify-between md:items-center gap-8 "
  >
   
  <div>
    <h1 class="titulus-quote">
        {{ character.nomen }}
    </h1>

    <div class="info-quote">
      <p class="descriptione">
        {{ character.descriptione }}
      </p>

      <div class="arca-quote" @click="router.push('/she-ra/gallery')">
        <p class="quote">
          {{ character.quote }}
        </p>
      </div>
    </div>

  </div>
    
  <figure class="figure-quote">
    <img class="w-[400px] h-[400px] justify-center object-contain"
     :src="`/imagines/she-ra/${character.imago}`" alt="" />
  </figure>
  </div>

  </div>
 
</template>

<style scoped>
.titulus-quote {
  font-weight: 700;
  font-size: 1.875rem;
  line-height: 2.25rem;
  margin-bottom: 1.25rem;
}

@media (min-width: 1024px) {
  .titulus-quote {
    font-size: 3rem;
    line-height: 1;
  }
}

.arca-quote {
  background-color: #d29ae4ee;
  padding: 1.25rem;
  border-radius: 0.5rem;
  cursor: pointer;
  border: 1px solid #8b349c;
  display: flex;
  justify-content: center;
  align-items: center;
  max-width: 48rem;
}
 
.quote {
  color: white;
  text-align: center;
  font-weight: 200;
  font-size: 1.8rem;
  line-height: 2.2rem;
  margin-bottom: 1.25rem; 
}
 
@media (min-width: 1024px) {
  .quote {
    font-size: 2.2rem;
    line-height: 2.5rem;
  }
}
 
.descriptione {
  font-size: 1.25rem;
  line-height: 1.75rem;
  font-weight: 300;
  margin-bottom: 2.5rem;
  max-width: 48rem;
}
 
@media (min-width: 1024px) {
  .descriptione {
    font-size: 1.5rem;
    line-height: 2rem;
  }
}
 
@media (min-width: 1024px) {
  .info-quote {
    max-width: 48rem;
  }
}

.figure-quote {
  display: flex;
  justify-content: center;
  min-width: min-content;
}

.figure-quote > img {
  object-fit: contain;
}
</style>
