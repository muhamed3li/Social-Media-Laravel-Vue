<script setup>
defineProps({
  image: String,
  title: String,
  description: String,
});
</script>


<template>
  <div class="mb-3 hover:bg-gray-100 cursor-pointer">
    <div class="flex items-start gap-3 py-2 px-3">
      <img :src="image" :alt="title" class="w-[43px] h-[43px] rounded-full" />
      <div>
        <h3 class="font-black text-xl">{{ title }}</h3>
        <div class="text-xs text-gray-500">{{ description }}</div>
      </div>
    </div>
  </div>
</template>
