<script setup lang="ts">
import {
  Carousel,
  CarouselContent,
  CarouselItem,
  CarouselNext,
  CarouselPrevious,
} from "@/components/ui/carousel";
import { Card, CardContent } from "@/components/ui/card";
import Autoplay from "embla-carousel-autoplay";

interface Props {
  photos: string[];
  basePath: string;
  autoPlayDelay?: number;
  loop?: boolean;
  dragFree?: boolean;
}

const props = withDefaults(defineProps<Props>(), {
  autoPlayDelay: 4000,
  loop: true,
  dragFree: true,
});
</script>







<template>
  

    <Carousel class=" w-200 h-100 max-md:xl max-lg:2xl object-cover items-center "
      :opts="{
        loop: props.loop,
        dragFree: props.dragFree,
      }"
       :plugins="[Autoplay({
      delay: props.autoPlayDelay,
    })]"
      >
        <CarouselContent>
          <CarouselItem v-for="(photo, index) in props.photos" :key="index">
            <div class="p-1 h-[320px] md:h-[420px]">
              <Card class="border-none h-full max-w-[600px] mx-auto">
                <CardContent
                  class="flex h-full items-center justify-center p-6"
                >
                  <img 
                  :src="`${props.basePath}/${photo}.png`"
                  :alt="`imagen ${index} de She-Ra`"
                  class="w-full h-full object-contain object-top"
                  >
                </CardContent>
              </Card>
            </div>
          </CarouselItem>
        </CarouselContent>
        <CarouselPrevious class="hidden md:flex justify-center item-center  bg-[#8b349c] text-white " />
        <CarouselNext class="hidden md:flex justify-center item-center  bg-[#8b349c] text-white" />
      </Carousel>
</template>