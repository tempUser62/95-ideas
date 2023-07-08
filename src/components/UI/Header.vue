<template>
  <div class="flex items-center w-screen h-16 border-b">
    <div class="logo">
      <img src="@/assets/svg/logo-home.svg" alt="logo" class="hidden md:block w-[470px]" />
      <span class="md:hidden sm:text-4xl">
      {{ companyName }}
      </span>
    </div>
    <div class="toggle" @click="toggleActive"></div>
    <div class="navigation" :class="{ active: isActive }">
      <ul>
        <li><router-link to="/" @click="toggleActive">Home</router-link></li>
        <li><router-link to="/services" @click="toggleActive">Services</router-link></li>
        <li><router-link to="/portfolio" @click="toggleActive">Portfolio</router-link></li>
        <li><router-link to="/contact" @click="toggleActive">Contact</router-link></li>
        <li><router-link to="/about" @click="toggleActive">About Us</router-link></li>
      </ul>
      <div class="social-bar">
        <ul>
          <li>
            <a href="https://facebook.com">
              <img src="@/assets/png/facebook.png" target="_blank" alt="" />
            </a>
          </li>
          <li>
            <a href="https://twitter.com">
              <img src="@/assets/png/twitter.png" target="_blank" alt="" />
            </a>
          </li>
          <li>
            <a href="https://instagram.com">
              <img src="@/assets/png/instagram.png" target="_blank" alt="" />
            </a>
          </li>
        </ul>
        <a href="mailto:you@email.com" class="email-icon">
          <img src="@/assets/png/email.png" alt="" />
        </a>
      </div>
    </div>
  </div>
</template>
<script lang="ts" setup>
import { Ref, ref } from 'vue';

const isActive: Ref<boolean> = ref(false);

function toggleActive() {
  isActive.value = !isActive.value;
};

const companyName = import.meta.env.VITE_COMPANY_NAME as string;
</script>
<style>
</style>
