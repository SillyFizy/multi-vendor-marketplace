<template>
  <header
      class="flex justify-center bg-[#FFFCF2] p-4 w-full h-20 shadow-l sticky top-0 z-50 transition-all ease-out duration-1000 h-1/12">
    <div class="h-full w-full xl:w-[80%] flex justify-between
    justify-items-stretch lg:justify-evenly xl:justify-between items-center">
      <div v-if="!isLG" class="flex h-[35%] md:h-[45%] flex-col justify-between mr-2 cursor-pointer"
           @click.stop="burgerClick">
        <div class="w-5 md:w-7 h-[2px] bg-black rounded-2xl"></div>
        <div class="w-5 md:w-7 h-[2px] bg-black rounded-2xl"></div>
        <div class="w-5 md:w-7 h-[2px] bg-black rounded-2xl"></div>
        <transition name="slide-fade">
          <ul v-if="burgerMenu" v-on-click-outside.bubble="burgerDrop"
              class="list-none absolute w-screen bg-[#FFFCF2] left-0 top-[80px] shadow-md p-4 z-10 flex flex-col items-start gap-5">
            <li v-for="category in categories" :key="category"
                class="text-black font-semibold hover:text-[#EB5E28] active:text-[#EB5E28]">{{ category.name }}
            </li>
          </ul>
        </transition>
      </div>
      <div :class="{'w-full':isSM}" class="flex items-center cursor-pointer justify-self-start">
        <img class="w-10 sm:w-12" src="../assets/logo.svg" alt="">
        <h1 id="siteName" class="text-2xl sm:text-3xl ms-1 sm:ms-2"><span class="text-[#EB5E28]">PC</span>HUB</h1>
       
      </div>
      <div v-if="!isSM" class="max-[768px]:ml-8">
        <div class="flex justify-start rounded-lg relative">
          <img src="../assets/search-md.svg "
               class="w-8 inner-shadow cursor-pointer absolute bg-[#d9d9d9] rounded-l-lg hover:bg-[#8c8c8c] transition-all duration-300 left-[-32px]"
               alt="">
          <input class="w-full inner-shadow bg-[#d9d9d9] rounded-r-lg h-8 outline-[#EB5E28]" placeholder=" Search"
                 type="text">
        </div>
      </div>
      <div class="flex justify-between gap-2 sm:gap-3 items-center">
        <div v-if="isSM" class="">
          <img class="max-w-[40px] cursor-pointer" src="../assets/search-md.svg " alt="">
        </div>
        <div>
          <img @click.stop="cartClick" class="max-w-[40px] sm:w-12 cursor-pointer relative"
               src="../assets/shopping-bag-03.svg"
               alt="">
          <transition name="slide-fade">
            <div
                class="absolute bg-[#a5a4a4] rounded-lg w-64 sm:w-80 lg:w-96 h-52 sm:h-72 lg:h-80 overflow-x-scroll top-16 right-14 min-[500px]:right-16 sm:right-20 lg:right-48 xl:right-52"
                v-if="isCart" v-on-click-outside.bubble="cartDrop">
              <div class="flex flex-col items-center w-full">
                <div class="w-11/12 h-24 bg-red-700 my-1 rounded-2xl">
                </div>
              </div>
            </div>
          </transition>
        </div>
        <div>
          <img @click.stop="userClick" class="max-w-[40px] sm:w-12 cursor-pointer relative"
               src="../assets/user-circle.svg"
               alt="">
          <transition name="slide-fade">
            <div
                class="absolute bg-[#a5a4a4] rounded-lg w-40 sm:w-44 lg:w-48 h-40 sm:h-44 lg:h-48 overflow-x-scroll top-16 right-6 min-[500px]:right-6 sm:right-6 lg:right-36 min-[1164px]:right-40 xl:right-48"
                v-if="isUser" v-on-click-outside.bubble="userDrop">
              <div class="flex flex-col items-center justify-center h-full w-full">
                <Button class="bg-[#6f6f6f] hover:bg-[#3c3c3c] text-white">Sign In</Button>
                <p>Or</p>
                <Button class="bg-[#EB5E28] hover:bg-[#9e3f1a]">Sign In</Button>
              </div>
            </div>
          </transition>
        </div>
      </div>
    </div>
  </header>
  <div v-if="isLG" class="bg-[#d9d9d9] w-full  h-12 flex justify-center items-center text-black font-semibold">
    <div class="flex w-[80%] justify-start">
      <ul class="flex w-[40%] justify-evenly">
        <li v-for="category in categories" :key="category"
            class="cursor-pointer hover:text-[#EB5E28] transition-all duration-200 justify-self-start">
          {{ category.name }}
        </li>
      </ul>
    </div>
  </div>
</template>
<script setup lang="ts">
import {computed, onMounted, ref} from "vue";
import Button from "./Button.vue";
import {onClickOutside, useMediaQuery} from "@vueuse/core";
import {vOnClickOutside} from '@vueuse/components'
import type {OnClickOutsideHandler} from '@vueuse/core'

const windowWidth = ref(window.innerWidth);
const isLG = useMediaQuery('(min-width: 1024px)')
const isMD = useMediaQuery('(min-width: 768px)')
const isSM = useMediaQuery('(max-width: 640px)')

const isCart = ref(false);
const isUser = ref(false);
const burgerMenu = ref(false)


const categories = ref([
  {name: "Computers", link: "none"},
  {name: "Storage", link: "none"},
  {name: "Laptops", link: "none"},
  {name: "Power", link: "none"},
])


window.addEventListener('resize', () => {
  windowWidth.value = window.innerWidth
});

const cartDrop: OnClickOutsideHandler = (event) => {
  isCart.value = false
}

const cartClick = () => {
  isCart.value = !isCart.value;
  isUser.value = false;
  burgerMenu.value = false;
}

const userDrop: OnClickOutsideHandler = (event) => {
  isUser.value = false
}

const userClick = () => {
  isUser.value = !isUser.value;
  isCart.value = false;
  burgerMenu.value = false;
}
const burgerDrop: OnClickOutsideHandler = (event) => {
  burgerMenu.value = false
}
const burgerClick = () => {
  burgerMenu.value = !burgerMenu.value;
  isCart.value = false;
  isUser.value = false;
}

</script>
<style>
.inner-shadow{
  box-shadow: inset 1px 1px 2px 1px #41413f71;
}
</style>
