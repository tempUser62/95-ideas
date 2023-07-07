<template>
  <section class="p-4 md: p-16">
    <div class="title">
      <h1 class="text-2xl mb-6">Some of our finest work</h1>
      <p class="mb-4">
        Creativity, they say, cannot be contained - and we wholeheartedly agree.
        Our portfolio is a testament to the diversity of our ideas and the
        breadth of our expertise. Each project is a vivid representation of our
        creative process - the initial brainstorm, the evolution of ideas, and
        the culmination of hard work and skill into a final product. Here, we've
        showcased a selection of our finest work, where every pixel, every line
        of code, every creative strategy was brought to life with our passion
        for innovation and our commitment to excellence.
      </p>
      <p>
        Take a journey through our achievements - from building visually
        stunning websites, to crafting engaging user interfaces, and developing
        game-changing apps. Each story is unique, each outcome is different, but
        the common thread that binds them all is our unwavering commitment to
        helping our clients reach their goals. We invite you to explore, to get
        inspired, and to discover the potential of what we could achieve
        together.
      </p>
    </div>

    <div class="portfolio">
      <div v-for="project in projects" :key="project.id" class="item">
        <img
          :src="project.preview_img"
          :alt="project.title"
          class="object-cover" />
        <div class="action">
          <router-link :to="'/project/' + project.id">
            {{ project.title }}
          </router-link>
        </div>
      </div>
    </div>
  </section>
</template>
<script lang="ts" setup>
import { projectsPortfolio } from '@/data';
import { Project } from '@/types';
import { onMounted, ref } from 'vue';

const projects = ref([]);

projects.value = projectsPortfolio.map((project: Project) => {
  return {
    ...project,
    preview_img: new URL(`/src/assets/projects/${project.preview}`, import.meta.url).href,
  };
});
</script>

<style scoped></style>
