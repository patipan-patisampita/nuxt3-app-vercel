<template>
  <section class="container py-10 mx-auto sm:py-16">
        <div v-if="post" class="sm:px-20">
            <!-- Blog Title -->
            <h1 class="mb-5 text-3xl font-bold leading-snug text-center" v-html="post.title.rendered"></h1>
            <!-- Blog Meta -->
            <div class="flex justify-center gap-5 mb-10">
                <span
                >Written by:
                <span class="text-primary-500">{{
                    post._embedded["author"][0]?.name
                }}</span></span
                >

                <span
                >Published on:
                <span class="text-primary-500">{{ post.date }}</span></span
                >
            </div>
            <!-- Blog Image -->
            <div
                class="blog__image h-[250px] sm:h-[500px] w-full rounded shadow-xl relative overflow-hidden mb-12"
            >
                <img
                :src="post._embedded['wp:featuredmedia'][0]?.source_url"
                :alt="post.title.rendered"
                class="absolute object-cover w-full h-full"
                />
            </div>
            <!-- Blog Content -->
            <div class="blog__content" v-html="post.content.rendered"></div>
        </div>
    </section>
</template>

<script setup lang="ts">
const params = useRoute().params;
const { data: posts } = await useWpApi().getPost(params.slug as string);
const post = posts.value?.[0];
useHead({
  title: post?.title.rendered,
  meta: [
    {
      name: "description",
      content: `${post?.excerpt.rendered}`,
    },
  ],
});
</script>

<style scoped></style>
