<template>
  <header
      class="flex justify-center bg-[#FFFCF2] p-4 w-full h-20 shadow-l sticky top-0 z-50 transition-all ease-out duration-1000 h-1/12">
    <div class="h-full w-full xl:w-[80%] flex justify-between lg:justify-evenly xl:justify-between items-center">
      <div class="flex justify-between items-center cursor-pointer">
        <img class="w-11 sm:w-14" src="../assets/logo.svg" alt="">
        <h1 id="siteName" class="text-2xl sm:text-3xl ms-1 sm:ms-2"><span class="text-[#EB5E28]">PC</span>HUB</h1>
        <!--the id is used to implement font but it didnt work for some reason go see https://fontsource.org/fonts/orbitron/install
        check the main.js file and the style.css file.-->
      </div>
      <div class="invisible sm:visible">
        <div class="flex justify-start rounded-lg relative">
          <img src="../assets/search-md.svg "
               class="w-8 shadow-inner cursor-pointer absolute bg-[#d9d9d9] rounded-l-lg hover:bg-[#8c8c8c] transition-all duration-300 left-[-32px]"
               alt="">
          <input class="w-full shadow-inner bg-[#d9d9d9] rounded-r-lg h-8 outline-[#EB5E28]" placeholder=" Search" type="text">
        </div>
      </div>
      <div class="flex justify-between gap-2 sm:gap-3 items-center">
        <div class="visible sm:invisible">
          <img class="w-14 cursor-pointer" src="../assets/search-md.svg " alt="">
        </div>
        <div>
          <img @click="isCartOpen" class="w-15 sm:w-12 cursor-pointer relative" src="../assets/shopping-bag-03.svg"
               alt="">
          <transition name="slide-fade">
            <div
                class="absolute bg-[#a5a4a4] rounded-lg w-64 sm:w-80 lg:w-96 h-52 sm:h-72 lg:h-80 overflow-x-scroll top-16 right-14 min-[500px]:right-16 sm:right-20 lg:right-48 xl:right-52"
                v-if="isCart" ref="cart">
              <div class="flex flex-col items-center w-full">
                <div class="w-11/12 h-24 bg-red-700 my-1 rounded-2xl">

                </div>
              </div>
            </div>
          </transition>
        </div>
        <div>
          <img @click="isUserOpen" class="w-15 sm:w-12 cursor-pointer relative" src="../assets/user-circle.svg" alt="">
          <transition name="slide-fade">
            <div
                class="absolute bg-[#a5a4a4] rounded-lg w-40 sm:w-44 lg:w-48 h-40 sm:h-44 lg:h-48 overflow-x-scroll top-16 right-6 min-[500px]:right-6 sm:right-6 lg:right-36 min-[1164px]:right-40 xl:right-48"
                v-if="isUser" ref="user">
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
</template>
<script setup>
import {computed, onMounted, ref} from "vue";
import Button from "./Button.vue";
import vClickOutside from "v-click-outside"
import {onClickOutside} from "@vueuse/core";

const windowWidth = ref(window.innerWidth);
const isCart = ref(false);
const isUser = ref(false);

const cart = ref(null);
const user = ref(null);




window.addEventListener('resize', () => {
  windowWidth.value = window.innerWidth
});

const isCartOpen = () => {
  if (isUser.value === true) {
    isUser.value = !isUser.value
  }
  return isCart.value = !isCart.value;
};
const isUserOpen = () => {
  if (isCart.value === true) {
    isCart.value = !isCart.value
  }
  return isUser.value = !isUser.value;
}

onClickOutside(user, event => {
  isUser.value = false;
})
onClickOutside(cart, event => {
  isCart.value = false;
})
</script>

