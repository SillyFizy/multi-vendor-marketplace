<template>
  <header
    class="flex justify-center bg-[#FFFCF2] p-4 w-full mb-8 h-[80px] shadow-l sticky top-0 z-50 transition-all ease-out duration-1000 h-1/12">
    <div class="h-full w-5/6 flex justify-between items-center ">
      <div class="flex justify-start items-center w-1/3 ">
        <img class="w-[12%] mr-5"  src="./assets/logo.svg" alt="">
        
        <h1 id="siteName" class="text-[50px]"><span class="text-[#EB5E28] text-[100%]">PC</span>HUB</h1>
        <!--the id is used to implement font but it didint work for some reason go see https://fontsource.org/fonts/orbitron/install
        cheak the main.js faile and the style.css file.-->
      </div>
      <div class="w-1/3 justify-start flex  "><input class="w-1/2 bg-[#d9d9d9] rounded-lg h-8 "  placeholder=" Search" type="text"></div>
      <div class=" w-1/3 flex justify-end items-center">
        <div class="mr-5 bg-[#EB5E28] w-1/5 h-8 justify-center flex items-center rounded-lg z-20 font-semibold"  >login</div>
        <div class="mr-5  w-1/5 h-8 justify-center flex items-center rounded-lg font-semibold z-20 bg-[#d9d9d9]">signup</div>
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
</script>