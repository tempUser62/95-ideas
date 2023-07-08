<template>
  <div
    class="flex w-screen overflow-hidden flex-col bg-gray-800 md:px-8 px-4 py-4 text-sm text-white underline-offset-4 md:px-4 justify-self-end">
    <div>
      <div
        class="flex flex-col flex-wrap justify-between md:pl-4 sm:flex-row w-full">
        <div
          class="mb-6 flex h-full flex-col justify-between md:mb-0 md:w-[30%]">
          <div class="mb-3 flex items-baseline">
            <SupportIcon class="mr-3 h-8 w-8 translate-y-1 text-white" />
            <span class="text-md font-bold text-gray-300 underline">
              Message us
            </span>
          </div>
          <SocialChat />
          <div class="mt-2 text-[#1dd7ff] font-bold text-lg">
            <!--            {{ companyName }}-->
            <img
              src="@/assets/svg/logo-home.svg"
              alt="logo"
              class="w-52 mt-2" />
          </div>
          <div class="justify-self-end text-gray-500 mt-2">
            2023 {{ legalName }}. All rights reserved
          </div>
        </div>

        <div class="mb-6 flex flex-col md:mb-0 md:w-[35%]">
          <div class="mb-2 flex items-baseline">
            <MailIcon
              class="mb-1 mr-2 h-8 w-8 translate-y-2 scale-95 text-white" />
            <span class="text-md font-bold text-gray-300 underline">
              Mail us
            </span>
          </div>
          <div
            v-for="item in emails"
            :key="item.mail"
            class="flex text-sm underline decoration-gray-400 underline-offset-4 mb-2"
            style="font-size: 0.925rem">
            <a :href="`mailto:${item.mail}`" class="text-teal-600">
              {{ item.mail }}
            </a>
            <span class="text-gray-400">&nbsp-&nbsp{{ item.caption }}</span>
          </div>
        </div>

        <div class="mb-6 flex flex-col text-sm md:mb-0 md:w-[30%]">
          <div class="mb-1 ml-1 flex items-baseline">
            <AddressIcon
              class="mr-3 h-8 w-8 translate-y-2 scale-90 text-white" />
            <span class="text-md mb-2 font-bold text-gray-300 underline">
              Addresses
            </span>
          </div>
          <div class="text-gray-400 mb-2">
            Ukraine: Melnikova 12, Office 33, Kyiv 04050
          </div>
          <div class="text-gray-400">Poland: Pomorska 43, 50-216 Wrocław</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import AddressIcon from '@/components/icons/Address.vue';
import MailIcon from '@/components/icons/Mail.vue';
import SubscribeIcon from '@/components/icons/Subscribe.vue';
import SupportIcon from '@/components/icons/Support.vue';
import LogoIcon from '@/components/icons/Logo.vue';

import SocialChat from '@/components/Chat/SocialChat.vue';

const companyName = import.meta.env.VITE_COMPANY_NAME as string;
const legalName = import.meta.env.VITE_LEGAL_NAME as string;
const companyShortName = import.meta.env.VITE_COMPANY_SHORT_NAME as string;

const emails = [
  {
    mail: `info@${companyShortName}.com`,
    caption: 'General inquiries',
  },
  {
    mail: `sales@${companyShortName}.com`,
    caption: 'for Sales Inquiries',
  },
  {
    mail: `tech@${companyShortName}.com`,
    caption: 'for technical support',
  },
  {
    mail: `pr@${companyShortName}.com`,
    caption: 'for PR inquiries',
  },
  {
    mail: `careers@${companyShortName}.com`,
    caption: 'would like to be a part of the team',
  },
];
</script>
<style></style>
