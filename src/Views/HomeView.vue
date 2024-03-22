<template>
  <section>
    <Carousel :autoplay="5000" :wrap-around="true" class="w-full h-1/2 shadow-inner ">
      <Slide v-for="img in images" :key="img" class="h-full w-full">
        <img :src="img.url"
             class="w-full  flex justify-center items-center"
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
import {ref} from "vue";

const images = ref([
  {url: "/src/assets/slide-demo-1.jpg", alt: "HWC"},
  {url: "/src/assets/slide-demo-2.jpg", alt: "Some random shit"},
  {url: "/src/assets/slide-demo-3.jpg", alt: "Some random shit"},
  {url: "/src/assets/slide-demo-4.jpg", alt: "Some random shit"},
  {url: "/src/assets/slide-demo-5.jpg", alt: "Some random shit"},
])
</script>