
<template>
  <AuthenticatedLayout>
    <div class="container mx-auto h-full overflow-auto">
      <div class="relative bg-white">
        <img
          :src="`https://timelinecovers.pro/facebook-cover/download/ultra-hd-space-facebook-cover.jpg`"
          class="w-full h-[200px] object-cover"
        />
        <div class="flex">
          <img
            :src="`https://cdn.iconscout.com/icon/free/png-512/free-avatar-370-456322.png?f=webp&w=256`"
            class="ml-[48px] w-[128px] h-[128px] -mt-[64px]"
            alt=""
          />
          <div class="flex justify-between items-center flex-1 p-4">
            <h2 class="font-bold text-lg">{{ user.name }}</h2>
            <PrimaryButton v-if="isMyProfile">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                class="w-4 h-4 mr-2"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="m16.862 4.487 1.687-1.688a1.875 1.875 0 1 1 2.652 2.652L6.832 19.82a4.5 4.5 0 0 1-1.897 1.13l-2.685.8.8-2.685a4.5 4.5 0 0 1 1.13-1.897L16.863 4.487Zm0 0L19.5 7.125"
                />
              </svg>
              Edit Profile
            </PrimaryButton>
          </div>
        </div>
      </div>
      <div class="border-t">
        <TabGroup>
          <TabList class="flex bg-white">
            <Tab
              v-if="authUser && authUser.id == user.id"
              v-slot="{ selected }"
            >
              <TabItem as="template" text="About" :selected="selected" />
            </Tab>
            <Tab as="template" v-slot="{ selected }">
              <TabItem text="Posts" :selected="selected" />
            </Tab>
            <Tab as="template" v-slot="{ selected }">
              <TabItem text="Followers" :selected="selected" />
            </Tab>
            <Tab as="template" v-slot="{ selected }">
              <TabItem text="Followings" :selected="selected" />
            </Tab>
            <Tab as="template" v-slot="{ selected }">
              <TabItem text="Photos" :selected="selected" />
            </Tab>
          </TabList>

          <TabPanels class="mt-2">
            <TabPanel v-if="authUser && authUser.id == user.id">
              <Edit :must-verify-email="mustVerifyEmail" :status="status" />
            </TabPanel>
            <TabPanel class="bg-white p-3 shadow"> Posts List </TabPanel>
            <TabPanel class="bg-white p-3 shadow"> Followers List </TabPanel>
            <TabPanel class="bg-white p-3 shadow"> Followings List </TabPanel>
            <TabPanel class="bg-white p-3 shadow"> Photos </TabPanel>
          </TabPanels>
        </TabGroup>
      </div>
    </div>
  </AuthenticatedLayout>
</template>

  
  <script setup>
import { computed, ref } from "vue";
import { TabGroup, TabList, Tab, TabPanels, TabPanel } from "@headlessui/vue";
import TabItem from "@/Pages/Profile/Partials/TabItem.vue";
import PrimaryButton from "@/Components/PrimaryButton.vue";
import { usePage } from "@inertiajs/vue3";
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import Edit from "@/Pages/Profile/Edit.vue";

const authUser = usePage().props.auth.user;

const isMyProfile = computed(() => authUser && authUser.id === props.user.id);

const props = defineProps({
  mustVerifyEmail: {
    type: Boolean,
  },
  status: {
    type: String,
  },
  user: {
    type: Object,
  },
});

const categories = ref({
  Recent: [
    {
      id: 1,
      title: "Does drinking coffee make you smarter?",
      date: "5h ago",
      commentCount: 5,
      shareCount: 2,
    },
    {
      id: 2,
      title: "So you've bought coffee... now what?",
      date: "2h ago",
      commentCount: 3,
      shareCount: 2,
    },
  ],
  Popular: [
    {
      id: 1,
      title: "Is tech making coffee better or worse?",
      date: "Jan 7",
      commentCount: 29,
      shareCount: 16,
    },
    {
      id: 2,
      title: "The most innovative things happening in coffee",
      date: "Mar 19",
      commentCount: 24,
      shareCount: 12,
    },
  ],
  Trending: [
    {
      id: 1,
      title: "Ask Me Anything: 10 answers to your questions about coffee",
      date: "2d ago",
      commentCount: 9,
      shareCount: 5,
    },
    {
      id: 2,
      title: "The worst advice we've ever heard about coffee",
      date: "4d ago",
      commentCount: 1,
      shareCount: 2,
    },
  ],
});
</script>
  