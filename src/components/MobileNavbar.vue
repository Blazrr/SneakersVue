<template>
  <div class="bg-white h-[3000vh] w-[300px]  p-6">
    <img src="../images/icon-close.svg" class="w-6 md:w-8 lg:hidden cursor-pointer" alt=""
      @click="$emit('closeNavbar')" />
    <div class="flex-col flex space-y-4 text-lg mt-8">
      <a href="#" class="navLink">Collections</a>
      <a href="#" class="navLink">Men</a>
      <a href="#" class="navLink">Woman</a>
      <a href="#" class="navLink">About</a>
      <a href="#" class="navLink">Contact</a>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped>

</style>
