<template>
  <div
    class="flex flex-col items-center rounded-full shadow-inner transition duration-300 transform hover:scale-[102%] cursor-pointer bg-gradient-to-t from-[#EB5E28] to-[#EB5E2830] h-[20vh] w-[20vh] mx-1"
  >
    <div class="w-full h-full">
      <img :src="catogaryPictuer" alt="" />
    </div>
    <div class="font-semibold text-lg">{{ catogaryName }}</div>
  </div>
</template>
<script setup>
const props = defineProps({
  catogaryPictuer: String,
  catogaryName: String,
  catogaryLink: String,
});
</script>
