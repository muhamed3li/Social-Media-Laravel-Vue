<script setup>
import { ref } from "vue";

const postCreating = ref(false);
</script>

<template>
  <div class="py-6 bg-white rounded-lg border p-4 mb-3">
    <div
      @click="postCreating = true"
      class="py-3 px-2 text-gray-500 border-2 border-gray-300 rounded mb-3"
    >
      Click here to create new post
    </div>
    <div v-if="postCreating" class="flex justify-between gap-2">
      <button
        type="submit"
        class="bg-indigo-500 relative hover:bg-indigo-700 text-white font-bold py-2 px-4 rounded"
      >
        Attach File
        <input
          type="file"
          class="absolute left-0 top-0 right-0 bottom-0 opacity-0"
        />
      </button>
      <button
        type="submit"
        class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
      >
        Submit
      </button>
    </div>
  </div>
</template>