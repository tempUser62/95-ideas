<template>
  <div class="my-2 flex">
    <a rel="noopener" target="_blank" :href="`https://t.me/${telegramUser}`">
      <TelegramIcon class="h-7 w-7 cursor-pointer" />
    </a>
    <a
      rel="noopener"
      target="_blank"
      :href="`https://api.whatsapp.com/send?phone=${whatsappNumber}&text=`">
      <WhatsAppIcon class="mx-5 h-7 w-7 cursor-pointer" />
    </a>
    <a rel="noopener" target="_blank" :href="`viber://chat?number=${viberNumber}`">
      <ViberIcon class="h-7 w-7 cursor-pointer" />
    </a>
  </div>
</template>

<script setup lang="ts">
import ViberIcon from '@/components/icons/Viber.vue';
import TelegramIcon from '@/components/icons/Telegram.vue';
import WhatsAppIcon from '@/components/icons/WhatsApp.vue';

const telegramUser = import.meta.env.VITE_TELEGRAM_USER as string;
const whatsappNumber = import.meta.env.VITE_WHATSAPP_NUMBER as string;
const viberNumber = import.meta.env.VITE_VIBER_NUMBER as string;
</script>
