<script setup>
import PostItem from "@/Components/app/PostItem.vue";

const post1 = {
  user: {
    id: 1,
    avatar: "https://i.pravatar.cc/70",
    name: "John Smith",
  },
  group: {
    id: 1,
    name: "Laravel Developer",
  },
  attachments: [
    {
      id: 1,
      name: "test.png",
      url: "https://picsum.photos/1000?",
      mime: "image/png",
    },
    {
      id: 2,
      name: "test2.png",
      url: "https://picsum.photos/1000",
      mime: "image/png",
    },
    {
      id: 2,
      name: "myDocument.docx",
      url: "#",
      mime: "application/lmsword",
    },
  ],
  body: `
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin molestie nulla ipsum, et bibendum augue ornare vel. Curabitur nec mi ac erat accumsan efficitur. Integer purus ante, volutpat eget sodales id, maximus et velit. Fusce id nisl ac lectus sagittis pellentesque. Nulla facilisi. Fusce nec ex justo. Praesent mattis justo nec neque pretium vestibulum.
      Nam eget facilisis lectus. Cras hendrerit mattis dui vitae aliquam. Mauris suscipit quam et euismod ultricies. In tincidunt neque nulla, ac mollis dui vehicula eu. Donec pretium iaculis erat, ac interdum metus.</p>
    `,
  created_at: "2024-3-1 15:12",
};
const post2 = {
  user: {
    id: 1,
    avatar: "https://i.pravatar.cc/50",
    name: "John Smith",
  },
  group: null,
  body: `
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin molestie nulla ipsum, et bibendum augue ornare vel. Curabitur nec mi ac erat accumsan efficitur. Integer purus ante, volutpat eget sodales id, maximus et velit. Fusce id nisl ac lectus sagittis pellentesque. Nulla facilisi. Fusce nec ex justo. Praesent mattis justo nec neque pretium vestibulum.
      Nam eget facilisis lectus. Cras hendrerit mattis dui vitae aliquam. Mauris suscipit quam et euismod ultricies. In tincidunt neque nulla, ac mollis dui vehicula eu. Donec pretium iaculis erat, ac interdum metus.</p>
    `,
  created_at: "2024-3-1 15:12",
};
</script>
<template>
  <div class="overflow-auto">
    <PostItem :post="post1" />
    <PostItem :post="post2" />
  </div>
</template>