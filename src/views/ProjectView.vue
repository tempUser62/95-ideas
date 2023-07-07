<template>
  <div class="relative p-8 mt-12 xs:mt-4 flex lg:flex-row flex-col-reverse">
    <div class="lg:w-2/3 px-8">
      <img :src="project.image_img" />
    </div>
    <div id="sticky" class="flex flex-col lg:w-1/3 lg:px-4 px-8 mb-8">
      <div class="lg:sticky lg:top-0">
        <h1 class="text-4xl font-bold mb-6">
          {{ project.title }}
        </h1>
        <h2 class="text-2xl font-bold mb-6">
          {{ project.subtitle }}
        </h2>
        <a
          class="text-md mb-8 text-blue-600 underline"
          :href="'https://' + project.url"
          target="_blank">
          {{ project.url }}
        </a>
        <p class="mb-4 mt-8">
          {{ project.p1 }}
        </p>
        <p class="mb-4">
          {{ project.p2 }}
        </p>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { useRoute } from 'vue-router';
import { projectsPortfolio } from '@/data';
import { Project } from '@/types';

const route = useRoute();
const slug = route.params.slug;
const project: Project = projectsPortfolio.find(
  (project: Project) => project.id === slug
);
project.image_img = new URL(`/src/assets/projects/${project.image}`, import.meta.url).href;
</script>

<style scoped></style>
