<template>
  <div
    v-if="store.showCart"
    class="absolute top-32 w-4/5 left-1/2 transform -translate-x-1/2 bg-white rounded-lg z-20"
  >
    <div v-if="store.count > 0">
      <p class="font-semibold p-4">Cart</p>
      <hr />
      <div class="flex p-4 text-slate-500 items-center space-x-4 justify-between">
        <img
          src="../images/image-product-1-thumbnail.jpg"
          alt=""
          class="h-12 w-12 rounded"
        />
        <div class="flex flex-col ml-4">
          <p>Fall Limited Edition Sneakers</p>
          <div>
            <span> $125.00</span> x <span>{{ store.count }}</span>
            <span class="ml-2 text-black">${{ store.count * 125 }}.00</span>
          </div>
        </div>
        <img
          src="../images/icon-delete.svg"
          alt=""
          class="h-6 cursor-pointer"
          @click="(store.count = 0), (store.showCart = false)"
        />
      </div>
      <div class="p-4 flex">
        <button class="w-4/5 mx-auto rounded-lg text-white bg-orange-400 p-4">
          Checkout
        </button>
      </div>
    </div>
    <div v-else class="p-4 flex items-center justify-between">
      <p>Your cart is empty</p>
      <img
        src="../images/icon-close.svg"
        alt=""
        class="h-6 cursor-pointer"
        @click="store.showCart = false"
      />
    </div>
  </div>
  <div
    v-if="store.showCart"
    class="absolute top-0 left-0 bg-slate-300 opacity-10 h-[3000vh] w-[3000vw] z-10"
    @click="store.showCart = false"
  ></div>
</template>

<script>
import { store } from "../Store";
export default {
  data() {
    return {
      store,
    };
  },
};
</script>

<style lang="scss" scoped></style>
