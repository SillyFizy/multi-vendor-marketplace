<template>
  <header
    class="flex justify-center bg-[#FFFCF2] p-4 w-full mb-8 h-[80px] shadow-l sticky top-0 z-50 transition-all ease-out duration-1000 h-1/12">
    <div class="h-full w-5/6 flex justify-between items-center ">
      <div class="flex justify-between items-center w-1/2 ">
        <img class="w-[10%] "  src="./assets/logo.svg" alt="">
        
        <h1 id="siteName" class="text-[50px] "><span class="text-[#EB5E28] text-[100%]">PC</span>HUB</h1>
        <div class="w-1/2 justify-start flex border-l-[#d9d9d9] border-l-[40px] rounded-lg relative ">
          <img src="./assets/search-md.svg " class="absolute left-[-35px] top-[2px]"  alt="">
          <input class="w-1/2 bg-[#d9d9d9] rounded-r-lg h-8 outline-[#EB5E28]  "  placeholder=" Search" type="text">
        </div>
        <!--the id is used to implement font but it didint work for some reason go see https://fontsource.org/fonts/orbitron/install
        cheak the main.js faile and the style.css file.-->
      </div>
      
      <div class=" w-1/3 flex justify-end items-center">
        <Button class="bg-[#EB5E28] hover:bg-[#B64518]">Login</Button>
        <Button class="ml-4 mr-4 bg-[#d4d4d4] hover:bg-[#a09f9f]">SignUp</Button>
        <div>
          <img class= "w-12 mr-5" src="./assets/user-circle.svg" alt="">
        </div>
        <div>
          <img class="w-12" src="./assets/shopping-bag-03.svg" alt="">
        </div>
      </div>
    </div>
  </header>
</template>
<script setup>
import Button from './components/Button.vue';
</script>