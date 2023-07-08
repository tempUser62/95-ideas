<template>
  <section class="home md:min-h[150vh] px-4 md:px-12">
    <img src="@/assets/jpg/home-img.jpg" class="home-img" alt="" />
    <div class="home-content">
      <h1 class="text-4xl mb-6">
        We help to achieve
        <br />
        your goals.
      </h1>
      <p>
        At the heart of every success story is a vision. A goal. It's the seed
        from which every empire, every innovation, every game-changing idea has
        grown. And here at our creative agency, we're in the business of making
        those dreams a reality. We are a team of artistic architects, designing
        a path towards your vision and sculpting ideas into tangible success.
        We're not just building campaigns or crafting content - we're creating a
        story. Your story.
      </p>
      <router-link to="/contact" class="btn">Get Started</router-link>
    </div>
  </section>
</template>

<script setup lang="ts"></script>

<style lang="scss">
section.home {
  flex-direction: row;
  @media (min-width: 768px) {
    min-height: 1188px;
  }
}

/* HOMEPAGE */

.home-content {
  position: relative;
  z-index: 10;
  max-width: 600px;
}

.home-img {
  position: absolute;
  bottom: 0;
  right: 0;
  height: 110%;
  margin-right: -1rem;
}
</style>
