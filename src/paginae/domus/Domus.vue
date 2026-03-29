<script lang="ts" setup>
import {Button} from '@/components/ui/button';


</script>

<template>
    <div class="fondo-home">
        <h1>
            <span>Diseños</span> Web y
            <br>
            Apps<span>Interactivas</span>

        </h1>
       <div class="botones">
        <Button >
            <router-link to="/indecision">Sí o No</router-link>
        </Button>
        <Button >
            <router-link to="/batman">Batman</router-link>
        </Button>
        <Button >
            <router-link to="/simpsons">Simpsons</router-link>
        </Button>
        <Button >
            <a href="https://www.upv.es">UPV</a>
        </Button>
    </div>
    </div>
    
</template>
<style scoped>
.fondo-home {
  background-color: rgb(21, 25, 52);
  height: 100vh;
  color: rgb(24, 182, 246);
}


.botones > Button {
  margin-right: 0.5rem;
  background-color: rgb(24, 182, 246);
} 


.botones > Button:hover {
  background-color: rgba(24, 182, 246, 0.7);
} 
</style>