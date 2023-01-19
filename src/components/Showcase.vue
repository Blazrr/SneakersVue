<template>
  <div class="lg:w-1/2 flex flex-col">
    <div>
      <swiper
        :style="{
          '--swiper-navigation-color': 'white',
          '--swiper-pagination-color': 'white',
        }"
        :spaceBetween="10"
        :navigation="true"
        :thumbs="{ swiper: thumbsSwiper }"
        :modules="modules"
        class="mySwiper2 lg:rounded-xl"
      >
        <swiper-slide>
          <img src="../images/image-product-1.jpg" />
        </swiper-slide>
        <swiper-slide>
          <img src="../images/image-product-2.jpg" />
        </swiper-slide>
        <swiper-slide>
          <img src="../images/image-product-3.jpg" />
        </swiper-slide>
        <swiper-slide>
          <img src="../images/image-product-4.jpg" />
        </swiper-slide>
      </swiper>

      <swiper
        @swiper="setThumbsSwiper"
        :spaceBetween="10"
        :slidesPerView="4"
        :freeMode="true"
        :watchSlidesProgress="true"
        :modules="modules"
        class="mySwiper mt-8 !p-4 lg:!p-0"
      >
        <swiper-slide>
          <img
            src="../images/image-product-1-thumbnail.jpg"
            class="rounded-lg bg-transparent"
          />
        </swiper-slide>
        <swiper-slide >
          <img src="../images/image-product-2-thumbnail.jpg" class="rounded-lg"  />
        </swiper-slide>
        <swiper-slide>
          <img src="../images/image-product-3-thumbnail.jpg" class="rounded-lg" />
        </swiper-slide>
        <swiper-slide>
          <img src="../images/image-product-4-thumbnail.jpg" class="rounded-lg" />
        </swiper-slide>
      </swiper>
    </div>
  </div>
</template>

<script>
import { Swiper, SwiperSlide } from "swiper/vue";

// Import Swiper styles
import "swiper/css";
import "swiper/css/free-mode";
import "swiper/css/navigation";
import "swiper/css/thumbs";
import { ref } from "vue";

// import required modules
import { FreeMode, Navigation, Thumbs } from "swiper";
export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const thumbsSwiper = ref(null);
    const setThumbsSwiper = (swiper) => {
      thumbsSwiper.value = swiper;
    };
    return {
      modules: [FreeMode, Navigation, Thumbs],
      Thumbs,
      thumbsSwiper,
      setThumbsSwiper,
    };
  },
};
</script>

<style lang="scss" scoped></style>
