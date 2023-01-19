<template>
  <div class="p-6 flex items-center justify-between md:p-8 w-full z-10">
    <div class="flex items-center space-x-4 md:space-x-8">
      <img src="../images/icon-menu.svg" alt="" class="w-6 md:w-8 lg:hidden cursor-pointer" @click="setNavbar" />
      <img src="../images/logo.svg" alt="" />
      <div class="lg:flex hidden  space-x-4 items-center text-lg">
        <a href="#" class="navLink">Collections</a>
        <a href="#" class="navLink">Men</a>
        <a href="#" class="navLink">Woman</a>
        <a href="#" class="navLink">About</a>
        <a href="#" class="navLink">Contact</a>
      </div>
    </div>

    <div class="flex items-center space-x-4 md:space-x-8">
      <div class="relative">
        <img src="../images/icon-cart.svg" alt="" class="w-6 md:w-10 cursor-pointer" @click="store.showCart = true" />
        <span v-if="store.count > 0" class="absolute -top-2 -right-2 bg-orange-300 rounded-lg px-1">{{
          store.count
        }}</span>
      </div>
      <img src="../images/image-avatar.png" alt="" class="w-8 md:w-12 cursor-pointer" />
    </div>
  </div>

  <hr class="w-4/5 mx-auto" />

  <div :class="[isActive ? 'left-0' : 'left-[-300px]']" class="absolute top-0 z-30 transition-all">
    <MobileNavbar @closeNavbar="closeNavbar" />
  </div>
  <div :class="[isActive ? 'block' : 'hidden']" class="z-20 bg-slate-300 h-[3000vh] w-[3000vw] bg-opacity-10 absolute"
    @click="closeNavbar"></div>
</template>

<script>
import MobileNavbar from "./MobileNavbar.vue";
import { store } from "../Store";

export default {
  data() {
    return {
      isActive: false,
      store,
    };
  },
  methods: {
    setNavbar() {
      this.isActive = true;
    },
    closeNavbar() {
      this.isActive = false;
    },
  },
  components: { MobileNavbar },
};
</script>
