<template>
  <header>
    <UIHeader />
  </header>

  <div class="main">
    <RouterView />
  </div>

  <UIFooter />
</template>

<script setup lang="ts">
import UIHeader from '@/components/UI/Header.vue';
import UIFooter from '@/components/UI/Footer.vue';
</script>

<style lang="scss">
#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  min-height: 100vh;
  width: 100vw;
  background-color: #f7fafc;
}
.main {
  width: 100vw;
  //min-height: calc(100vh - 64px - 146px);
  //@media (max-width: 1536px) {
  //  min-height: calc(100vh - 64px - 223px);
  //}
  //@media (max-width: 960px) {
  //  min-height: calc(100vh - 64px - 381px);
  //}
  @media (max-width: 768px) {
    padding: 0 !important;
    align-items: center;
    //min-height: calc(100vh - 64px - 783px);
  }
}
</style>
