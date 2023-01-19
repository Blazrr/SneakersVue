<template>
  <div class="mt-8">
    <h3 class="text-orange-300 font-semibold tracking-wider text-xl">SNEAKER COMPANY</h3>
    <h1 class="font-bold text-3xl mt-4">Fall Limited Edition Sneakers</h1>
    <p class="mt-4 text-slate-500">
      These low-profile sneakers are your perfect casual wear companion, Featuribg a
      durable outer sole, they'll withstand everything the weather can offer.
    </p>
    <div>
      <div class="flex justify-between items-center mt-4">
        <div class="flex space-x-4 items-center">
          <p class="font-bold text-2xl">$125.00</p>
          <p class="font-bold text-orange-300 text-xl bg-orange-100 p-1 rounded">50%</p>
        </div>
        <p class="text-slate-400 text-xl font-semibold">$250.00</p>
      </div>

      <div class="lg:flex lg:space-x-6">
        <div class="flex justify-between bg-slate-200 p-4 rounded items-center mt-4 lg:w-2/5">
          <button class="text-orange-400 text-3xl" @click="count--">-</button>
          <span class="text-xl font-bold">
            {{ count }}
          </span>
          <button class="text-orange-400 text-3xl" @click="count++">+</button>
        </div>

        <button
          class="w-full mt-4 rounded-lg bg-orange-400 p-4 hover:bg-orange-300 transition-all flex justify-center items-center space-x-4"
          @click="setItems">
          <img src="../images/icon-cart.svg" alt="" class="text-white" />
          <span class="text-white font-semibold"> Add to cart </span>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import { store } from "../Store";

export default {
  data() {
    return {
      count: 0,
      store,
    };
  },
  computed: {
    finalCount() {
      if (this.count < 0) {
        this.count = 0;
        return 0;
      }
      return this.count;
    },
  },
  methods: {
    setItems() {
      this.store.count += this.count;
      this.count = 0;
    },
  },
};
</script>
