<template>
  <section>
    <Carousel
      :autoplay="5000"
      :wrap-around="true"
      class="w-full h-1/2 shadow-inner"
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
    <section class="w-full flex flex-col">
      <Carousel
      class="px-10 py-2 m-4 rounded-lg bg-gradient-to-t from-[#EB5E2895] to-[#EB5E2830]" 
      v-bind="settings" :breakpoints="breakpoints">
      <Slide v-for="product in products" :key="product.id" class="h-[200px] w-[125px] ">
        <ProductCard class="carousel__item h-full w-full rounded-xl" :productPicture="product.productPicture" :productName="product.productName" :price="product.price" :inStock="product.inStock"> </ProductCard>
      </Slide>

      <template #addons>
        <Navigation />
      </template>
    </Carousel>
    </section>
    <section class="w-full flex flex-col my-4">
      <Carousel
      class="px-10 py-2 m-4 rounded-lg bg-gradient-to-t from-[#EB5E2895] to-[#EB5E2830]" 
      v-bind="settings" :breakpoints="breakpoints">
      <Slide v-for="product in products" :key="product.id" class="h-[200px] w-[125px] ">
        <ProductCard class="carousel__item h-full w-full rounded-xl" :productPicture="product.productPicture" :productName="product.productName" :price="product.price" :inStock="product.inStock"> </ProductCard>
      </Slide>

      <template #addons>
        <Navigation />
      </template>
    </Carousel>
    </section>
  </section>
  <section class="h-1/2 w-screen"></section>
  <section class="w-full h-[80vh] mt-5 flex justify-center">
    <div
      class="h-[50%] flex flex-col items-center gap-4 w-[90%] md:flex-row md:justify-evenly p-5"
    >
      <img
        class="hover:scale-105 transition-all ease-in duration-200 w-3/4 md:w-2/4 lg:w-5/12 xl:w-2/6"
        src="../assets/Vendor Registeration.svg"
        alt=""
      />

      <img
        class="hover:scale-105 transition-all ease-in duration-200 w-3/4 md:w-2/4 lg:w-5/12 xl:w-2/6"
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
      700: {
        itemsToShow: 5,
        snapAlign: 'center',
      },
      1024: {
        itemsToShow: 7,
        snapAlign: 'start',
      },
      1280: {
        itemsToShow: 8,
        snapAlign: 'start',
      },
      1366: {
        itemsToShow: 9,
        snapAlign: 'start',
      },
      1440: {
        itemsToShow: 10,
        snapAlign: 'start',
      },
    })
const products = ref ([
  {
    id: 1,
    productPicture: '/src/assets/kv-main.png',
    productName: 'ASUS TUF',
    price: "100",
    inStock: true,
  },
  {
    id: 2,
    productPicture: '/src/assets/kv-main.png',
    productName: 'ASUS TUF GPU',
    price: '1200',
    inStock: true,
  },
  {
    id: 2,
    productPicture: '/src/assets/kv-main.png',
    productName: 'ASUS TUF GPU',
    price: '1200',
    inStock: true,
  },
  {
    id: 2,
    productPicture: '/src/assets/kv-main.png',
    productName: 'ASUS TUF GPU',
    price: '1200',
    inStock: true,
  },
  {
    id: 2,
    productPicture: '/src/assets/kv-main.png',
    productName: 'ASUS TUF GPU',
    price: '1200',
    inStock: true,
  },
  {
    id: 2,
    productPicture: '/src/assets/kv-main.png',
    productName: 'ASUS TUF GPU',
    price: '1200',
    inStock: true,
  },
  {
    id: 2,
    productPicture: '/src/assets/kv-main.png',
    productName: 'ASUS TUF GPU',
    price: '1200',
    inStock: true,
  },
  {
    id: 2,
    productPicture: '/src/assets/kv-main.png',
    productName: 'ASUS TUF GPU',
    price: '1200',
    inStock: true,
  },{
    id: 2,
    productPicture: '/src/assets/kv-main.png',
    productName: 'ASUS TUF GPU',
    price: '1200',
    inStock: true,
  },{
    id: 2,
    productPicture: '/src/assets/kv-main.png',
    productName: 'ASUS TUF GPU',
    price: '1200',
    inStock: true,
  },{
    id: 2,
    productPicture: '/src/assets/kv-main.png',
    productName: 'ASUS TUF GPU',
    price: '1200',
    inStock: true,
  },{
    id: 2,
    productPicture: '/src/assets/kv-main.png',
    productName: 'ASUS TUF GPU',
    price: '1200',
    inStock: true,
  },{
    id: 2,
    productPicture: '/src/assets/kv-main.png',
    productName: 'ASUS TUF GPU',
    price: '1200',
    inStock: true,
  },{
    id: 2,
    productPicture: '/src/assets/kv-main.png',
    productName: 'ASUS TUF GPU',
    price: '1200',
    inStock: true,
  },{
    id: 2,
    productPicture: '/src/assets/kv-main.png',
    productName: 'ASUS TUF GPU',
    price: '1200',
    inStock: true,
  },{
    id: 2,
    productPicture: '/src/assets/kv-main.png',
    productName: 'ASUS TUF GPU',
    price: '1200',
    inStock: true,
  },
]);
</script>
