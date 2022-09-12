<template>
  <guest-layout>
    <section class="flex md:flex-row m-2 p-2 ">
      <div class="w-full lg:w-8/12">
        <PostCard v-for="post in posts.data" :post="post" :community="post.community_slug" :key="post.id" />
      </div>
      <div class="w-4/12 p-4 hidden lg:block">
        <CommunityList :communities="communities.data">
          <template #title>Top communities</template>
        </CommunityList>

      

        <!-- <div class="w-full bg-white shadow-md border rounded-lg mt-10">
         
            <h2 class="font-semibold text-lg p-6 bg-indigo-700 text-white rounded-lg">
      testess titulko
      </h2>
      <ul class="divide-y divide-slate-300 dark:divide-slate-700 p-4">
        <li class="py-3 sm:py-4">
          testes li
        </li>
        <li class="py-3 sm:py-4">
          testes li
        </li>
        <li class="py-3 sm:py-4">
          testes li
        </li>
      </ul>
        </div> -->
      </div>

      

    </section>
  </guest-layout>
</template>
  
<script setup>
import GuestLayout from "@/Layouts/Guest.vue";
import PostCard from "@/Components/PostCard.vue";
import Pagination from "@/Components/Pagination.vue";
import CommunityList from "@/Components/CommunityList.vue";
defineProps({
  communities: Object,
  posts: Object,
});
</script>