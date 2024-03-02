<script setup>
import GroupItem from "@/Components/app/GroupItem.vue";
import TextInput from "@/Components/TextInput.vue";
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
      You are not joined to any groups
    </div>
    <div v-else>
      <GroupItem
        image="https://picsum.photos/500/300?random=1"
        title="Laravel Developers"
        description="Lorem, ipsum dolor sit amet consectetur."
      />
      <GroupItem
        image="https://picsum.photos/500/300?random=2"
        title="Vue.js Developers"
        description="Lorem, ipsum dolor sit amet consectetur."
      />

      <GroupItem
        image="https://picsum.photos/500/300?random=2"
        title="Vue.js Developers"
        description="Lorem, ipsum dolor sit amet consectetur."
      />

      <GroupItem
        image="https://picsum.photos/500/300?random=2"
        title="Vue.js Developers"
        description="Lorem, ipsum dolor sit amet consectetur."
      />

      <GroupItem
        image="https://picsum.photos/500/300?random=8"
        title="Vue.js Developers"
        description="Lorem, ipsum dolor sit amet consectetur."
      />

      <GroupItem
        image="https://picsum.photos/500/300?random=2"
        title="Vue.js Developers"
        description="Lorem, ipsum dolor sit amet consectetur."
      />

      <GroupItem
        image="https://picsum.photos/500/300?random=23"
        title="Vue.js Developers"
        description="Lorem, ipsum dolor sit amet consectetur."
      />

      <GroupItem
        image="https://picsum.photos/500/300?random=3"
        title="Vue.js Developers"
        description="Lorem, ipsum dolor sit amet consectetur."
      />
    </div>
  </div>
</template>