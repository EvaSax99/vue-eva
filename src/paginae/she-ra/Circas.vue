<script setup lang="ts">
import { ref } from 'vue'

const imagoCirca = ref<string>('adora.png')
</script>

<template>
    <div class="flex flex-col lg:flex-row lg:justify-between max-w-[1400px] md: items-center w-full md: mx-auto my-8 gap-8 px-5 md:px-20">
    <figure class="flex justify-center min-w-min order-2 lg:order-1 h-[400px] lg:h-[500px]">
        <img 
        :src="`/imagines/she-ra/${ imagoCirca }`" 
        alt="Adora"
        class="object-contain"
		@mouseenter="imagoCirca = 'poster.png'"
		@mouseleave="imagoCirca = 'poster2.png'"
		>
    </figure> 
    <div class="flex flex-col gap-4 order-1 text-center lg:text-left">

	<h1 class="font-bold text-xl lg:text-5xl mb-5 text-[#8b349c]"> 
		About the She-Ra Quote App
	</h1>

	<div class="lg:max-w-3xl">
		<p class="mb-5">
			She-Ra: Princess of Power  is an American animated superhero television series developed by ND Stevenson and produced by DreamWorks Animation Television for Netflix. It is a reboot of the 1985 Filmation series She-Ra: Princess of Power, and like the original series, it tells the tale of Adora, an adolescent who can transform into the heroine She-Ra and leads a group of other magical princesses in a rebellion against the evil Lord Hordak and his Horde.

		</p>
                
		<p class="mb-5">
			Knowing quotes from She-Ra can be cool for a few reasons. First, it can help you connect with other fans of the show and spark conversations about favorite episodes, characters, and jokes. Second, many of the show's quotes have become iconic and are often referenced in popular culture, so knowing them can make you feel more in tune with current trends and references.
		</p>

		<p class="mb-5">
			Furthermore, She-Ra has often tackled social and political issues through satire and parody, making its quotes more than just funny one-liners. Being familiar with the show's commentary on current events and societal trends can also make you more aware and engaged with the world around you.
		</p>


	</div>
</div>   
    

    </div>
</template>



<style scoped>

</style>