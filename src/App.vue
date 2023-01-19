<script setup>
import Description from './components/Description.vue';
import Navbar from './components/Navbar.vue';
import Cart from './components/Cart.vue'
import Showcase from './components/Showcase.vue';




</script>

<template>
  <Navbar />
  <Cart />
  <div class="lg:flex items-center lg:space-x-10 lg:w-4/5 lg:mx-auto lg:mt-16 ">
  <Showcase/>
  <div class="w-4/5 lg:w-full mx-auto">
    <Description />
  </div>
</div>
</template>

<style scoped>


</style>
