<template>
  <section>
    <Carousel :autoplay="5000" :wrap-around="true" class="w-screen h-1/2 md:bg-[#eb5f28d7] shadow-inner ">
      <Slide v-for="img in images" :key="img" class="h-full w-full">
        <img :src="img.url"
             class="w-full md:w-3/4 lg:w-1/2 h-full md:h-3/4 lg:h-1/2 flex justify-center items-center m-2 mt-3 mb-0 rounded-lg"
             :alt="img.alt">
      </Slide>
      <template #addons>
        <Pagination/>
      </template>
    </Carousel>
  </section>
  <section class="h-1/2 w-screen">
  </section>
</template>

<script setup>
import {Carousel, Pagination, Slide} from "vue3-carousel";
import 'vue3-carousel/dist/carousel.css'
import {defineComponent, ref} from "vue";

const images = ref([
  {url: "/src/assets/slide-demo-1.jpg", alt: "HWC"},
  {url: "/src/assets/slide-demo-2.jpg", alt: "Some random shit"},
  {url: "/src/assets/slide-demo-3.jpg", alt: "Some random shit"},
  {url: "/src/assets/slide-demo-4.jpg", alt: "Some random shit"},
])
</script>
