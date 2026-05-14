<script lang="ts" setup>
import { RouterLink } from 'vue-router';
import {Button} from '@/components/ui/button';
import LogoSimpsons from '@/components/LogoSimpsons.vue';


</script>

<template>
<div class="bg-[#ffde00] min-h-screen text-center p-4 flex flex-col items-center justify-center">
<LogoSimpsons estilus="w-[24rem]"  />
	<h1 class="text-xl my-1 font-medium">
    	Discover some of the most amazing Quotes from The Simpsons
	</h1>
	<div>
    	<strong>This is an unofficial app (even though it looks so cool!)</strong>
	</div>
	<div class="mt-8 flex gap-5">
		<Button variant="simpsonsfont" size="elongatis">
      		<RouterLink to="/">Exit</RouterLink>
    	</Button>
    	<Button variant="simpsonsfont" size="elongatis">
      		<RouterLink to="/simpsons/about">Enter</RouterLink>
    	</Button>
	</div>
	<div class="flex gap-12 mt-8">
		<img class="object-contain hidden md:block" src="/imagines/simpsons/bart.png" alt="Bart" width="200px">
		<img class="object-contain hidden md:block mt-20" src="/imagines/simpsons/lisa.png" alt="Lisa" width="200px">
		<img class="object-contain hidden md:block mt-0" src="/imagines/simpsons/homer.png" alt="Homer" width="200px">


</div>

</div>


</template>
