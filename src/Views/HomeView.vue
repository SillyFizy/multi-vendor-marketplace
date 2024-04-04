<template>
  <section>
    <Carousel
      :autoplay="5000"
      :wrap-around="true"
      class="w-full h-1/2 inner-shadow"
    >
      <Slide v-for="img in images" :key="img" class="h-full w-full">
        <img
          :src="img.url"
          class="w-full flex justify-center items-center"
          :alt="img.alt"
        />
      </Slide>
      <template #addons>
        <Pagination />
      </template>
    </Carousel>
    <section class="w-full flex flex-col my-4">
      <h1 class="text-xl font-semibold ps-2">Computer Builds</h1>
      <Carousel
      class="px-2 py-2 my-2 mx-1 rounded-lg bg-gradient-to-t from-[#EB5E2840] to-[#EB5E2810] bg-opacity-5"
      v-bind="settings" :breakpoints="breakpoints">
      <Slide v-for="product in products" :key="product.id" class="">
        <ProductCard class="carousel__item rounded-lg" :productPicture="product.productPicture" :productName="product.productName" :price="product.price" :inStock="product.inStock"> </ProductCard>
      </Slide>

      <template #addons>
        <Navigation />
      </template>
    </Carousel>
    </section>
  </section>
  <section class="w-screen h-[60vh]">
    <div class="w-full h-full grid grid-cols-2 grid-rows-3 place-items-center">
      <div class="w-[130px] h-[130px] bg-gradient-to-t from-[#EB5E2870] to-[#EB5E2830] rounded-full flex flex-col inner-shadow transition-all ease-in cursor-pointer hover:scale-105">
        <img src="@/assets/Motherboard6.png" alt="">
      <h3 class="w-fit self-center">Motherboard</h3>
      </div>
      <div class="w-[130px] h-[130px] bg-gradient-to-t from-[#EB5E2870] to-[#EB5E2830] rounded-full flex flex-col inner-shadow transition-all ease-in cursor-pointer hover:scale-105">
        <img src="@/assets/Motherboard6.png" alt="">
      <h3 class="w-fit self-center">Motherboard</h3>
      </div>
      <div class="w-[130px] h-[130px] bg-gradient-to-t from-[#EB5E2870] to-[#EB5E2830] rounded-full flex flex-col inner-shadow transition-all ease-in cursor-pointer hover:scale-105">
        <img src="@/assets/Motherboard6.png" alt="">
      <h3 class="w-fit self-center">Motherboard</h3>
      </div>
      <div class="w-[130px] h-[130px] bg-gradient-to-t from-[#EB5E2870] to-[#EB5E2830] rounded-full flex flex-col inner-shadow transition-all ease-in cursor-pointer hover:scale-105">
        <img src="@/assets/Motherboard6.png" alt="">
      <h3 class="w-fit self-center">Motherboard</h3>
      </div>
      <div class="w-[130px] h-[130px] bg-gradient-to-t from-[#EB5E2870] to-[#EB5E2830] rounded-full flex flex-col inner-shadow transition-all ease-in cursor-pointer hover:scale-105">
        <img src="@/assets/Motherboard6.png" alt="">
      <h3 class="w-fit self-center">Motherboard</h3>
      </div>
      <div class="w-[130px] h-[130px] bg-gradient-to-t from-[#EB5E2870] to-[#EB5E2830] rounded-full flex flex-col inner-shadow transition-all ease-in cursor-pointer hover:scale-105">
        <img src="@/assets/Motherboard6.png" alt="">
      <h3 class="w-fit self-center">Motherboard</h3>
      </div>
    </div>
  </section>
  <section>
    <section class="w-full flex flex-col my-4">
      <h1 class="text-xl font-semibold ps-2">Computer Builds</h1>
      <Carousel
          class="px-2 py-2 my-2 mx-1 rounded-lg bg-gradient-to-t from-[#EB5E2840] to-[#EB5E2810] bg-opacity-5"
          v-bind="settings" :breakpoints="breakpoints">
        <Slide v-for="product in products" :key="product.id" class="">
          <ProductCard class="carousel__item rounded-lg" :productPicture="product.productPicture" :productName="product.productName" :price="product.price" :inStock="product.inStock"> </ProductCard>
        </Slide>

        <template #addons>
          <Navigation />
        </template>
      </Carousel>
    </section>
    <section class="w-full flex flex-col my-4">
      <h1 class="text-xl font-semibold ps-2">Computer Builds</h1>
      <Carousel
          class="px-2 py-2 my-2 mx-1 rounded-lg bg-gradient-to-t from-[#EB5E2840] to-[#EB5E2810] bg-opacity-5"
          v-bind="settings" :breakpoints="breakpoints">
        <Slide v-for="product in products" :key="product.id" class="">
          <ProductCard class="carousel__item rounded-lg" :productPicture="product.productPicture" :productName="product.productName" :price="product.price" :inStock="product.inStock"> </ProductCard>
        </Slide>

        <template #addons>
          <Navigation />
        </template>
      </Carousel>
    </section>
  </section>
  <section class="w-full h-[25vh] min-[444px]:h-[30vh] min-[500px]:h-[35vh] min-[560px]:h-[40vh] min-[610px]:h-[50vh] min-[768px]:h-[20vh] xl:h-[30vh] mt-5 flex justify-center items-center">
    <div
      class="h-[50%] flex flex-col items-center gap-4 w-[90%] md:flex-row md:justify-evenly p-5"
    >
      <img
        class="hover:scale-105 transition-all ease-in duration-200 w-full md:w-2/4 lg:w-5/12 xl:w-2/6"
        src="../assets/Vendor Registeration.svg"
        alt=""
      />

      <img
        class="hover:scale-105 transition-all ease-in duration-200 w-full md:w-2/4 lg:w-5/12 xl:w-2/6"
        src="../assets/deals.svg"
        alt=""
      />
    </div>
  </section>
</template>

<script setup>
import { Carousel, Pagination, Navigation, Slide } from "vue3-carousel";
import "vue3-carousel/dist/carousel.css";
import { ref } from "vue";
import ProductCard from "@/components/ProductCard.vue";
import CatograyCard from "@/components/CatograyCard.vue";
const images = ref([
  { url: "/src/assets/slide-demo-1.jpg", alt: "HWC" },
  { url: "/src/assets/slide-demo-2.jpg", alt: "Some random shit" },
  { url: "/src/assets/slide-demo-3.jpg", alt: "Some random shit" },
  { url: "/src/assets/slide-demo-4.jpg", alt: "Some random shit" },
  { url: "/src/assets/slide-demo-5.jpg", alt: "Some random shit" },
]);
const settings = ref({
  itemsToShow:3,
  snapAlign:'center'
})
const breakpoints = ref({
      390: {
        itemsToShow: 2.5,
        snapAlign: 'end',
      },
      450: {
        itemsToShow: 3,
        snapAlign: 'end',
      },
      550: {
        itemsToShow: 4,
        snapAlign: 'end',
      },
      700: {
        itemsToShow: 5,
        snapAlign: 'start',
      },
      930: {
        itemsToShow: 6,
        snapAlign: 'start',
      },
      1024: {
        itemsToShow: 7,
        snapAlign: 'start',
      },
      1280: {
        itemsToShow: 7,
        snapAlign: 'start',
      },
      1366: {
        itemsToShow: 9,
        snapAlign: 'start',
      },
      1440: {
        itemsToShow: 12,
        snapAlign: 'start',
      },
    })
const products = ref ([
  {
    id: 1,
    productPicture: '/src/assets/kv-main.png',
    productName: 'TUF GAMING B650-E WIFI',
    price: "100",
    inStock: true,
  },
  {
    id: 2,
    productPicture: '/src/assets/kv-main.png',
    productName: 'TUF GAMING B650-E WIFI',
    price: '1200',
    inStock: true,
  },
  {
    id: 3,
    productPicture: '/src/assets/kv-main.png',
    productName: 'TUF GAMING B650-E WIFI',
    price: '1200',
    inStock: true,
  },
  {
    id: 3,
    productPicture: '/src/assets/kv-main.png',
    productName: 'TUF GAMING B650-E WIFI',
    price: '1200',
    inStock: true,
  },{
    id: 3,
    productPicture: '/src/assets/kv-main.png',
    productName: 'TUF GAMING B650-E WIFI',
    price: '1200',
    inStock: true,
  },{
    id: 3,
    productPicture: '/src/assets/kv-main.png',
    productName: 'TUF GAMING B650-E WIFI',
    price: '1200',
    inStock: true,
  },{
    id: 3,
    productPicture: '/src/assets/kv-main.png',
    productName: 'TUF GAMING B650-E WIFI',
    price: '1200',
    inStock: true,
  },
]);
</script>
<style>
.inner-shadow{
  box-shadow: inset 1px 1px 2px 1px #41413f71;
}
</style>
