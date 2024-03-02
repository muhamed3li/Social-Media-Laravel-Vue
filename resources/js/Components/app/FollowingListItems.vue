<script setup>
import TextInput from "@/Components/TextInput.vue";
import FollowingItem from "@/Components/app/FollowingItem.vue";
import { ref } from "vue";

const searchKeyword = ref("");
</script>
<template>
  <TextInput
    :model-value="searchKeyword"
    placeholder="Type to search..."
    class="w-full mt-4"
  />

  <div class="mt-3 flex-1 overflow-auto">
    <div v-if="false" class="text-gray-600 text-center p-3">
      You don't have any friends yet!
    </div>
    <div v-else>
      <FollowingItem image="https://i.pravatar.cc/506" title="John  Doe" />
      <FollowingItem image="https://i.pravatar.cc/44" title="Elon  Musk" />

      <FollowingItem image="https://i.pravatar.cc/33" title="Alice Johnson" />
      <FollowingItem
        image="https://i.pravatar.cc/66"
        title="Robert Downey Jr."
      />
      <FollowingItem image="https://i.pravatar.cc/43" title="Mark Zuckerberg" />
    </div>
  </div>
</template>

<style scoped>
</style>