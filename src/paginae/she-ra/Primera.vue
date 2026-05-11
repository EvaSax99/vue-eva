<script lang="ts" setup>
import { RouterLink } from 'vue-router';
import {Button} from '@/components/ui/button';




</script>

<template>
<div class="bg-[#fff] min-h-screen text-center p-4 flex flex-col items-center justify-center ">
<img 
src="/imagines/she-ra/SheRa-logo.png"
 alt="She-Ra Logo"
 class="pb-10">
	<h1 class="text-xl my-1 font-medium">
    	Discover some of the most amazing Quotes from She-Ra and the Princesses of Power
	</h1>
	<div>
    	<strong>This is an unofficial app (even though it looks so cool!)</strong>
	</div>
	<div class="mt-8 flex gap-5">
		<Button variant="simpsonsfont" 
		size="elongatis"
		class=" text-[#8b349c] border-[#8b349c] hover:bg-[#d29ae4ee] hover:text-white hover:border-[#8b349c]"
		>
      		<RouterLink to="/">Exit</RouterLink>
    	</Button>
    	<Button variant="simpsonsfont"
		 size="elongatis"
		 class="text-[#8b349c] border-[#8b349c] hover:bg-[#d29ae4ee] hover:text-white hover:border-[#8b349c]"
		 >
      		<RouterLink to="/simpsons/about">Enter</RouterLink>
    	</Button>
	</div>
	<div class="flex gap-12 mt-8">
		<img class="object-contain hidden md:block" src="/imagines/she-ra/adora.png" alt="Adora" width="250px">
		<img class="object-contain hidden md:block mt-20" src="/imagines/she-ra/catra.png" alt="Catra" width="400px">
		<img class="object-contain hidden md:block mt-0" src="/imagines/she-ra/glimmer.png" alt="Glimmer" width="200px">


</div>

</div>


</template>
