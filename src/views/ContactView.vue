<template>
  <div class="w-screen py-4 md:p-16 !pt-0">
    <div v-if="mode === 'form'" class="flex w-full border">
      <img
        :src="PhoneImg"
        alt="Phone"
        class="hidden w-2/6 object-cover md:block" />
      <form
        id="contact"
        class="flex w-full flex-col items-center px-12 py-8 md:w-4/6">
        <h2 class="mb-4 text-center text-2xl font-bold">Contact Us</h2>
        <div class="mb-4 mt-6 w-full">
          <label class="mb-2 block text-accent-blue-700" for="name">Name</label>
          <input
            class="focus:shadow-outline appearance-none rounded border px-3 py-2 leading-tight text-gray-700 shadow focus:outline-none lg:w-full"
            id="name"
            type="text"
            v-model="form.name"
            placeholder="Enter your name"
            required />
        </div>
        <div class="mb-4 mt-6 w-full">
          <label class="mb-2 block text-accent-blue-700" for="email">
            Email
            <span class="text-danger-500">*</span>
          </label>
          <input
            class="focus:shadow-outline w-full appearance-none rounded border px-3 py-2 leading-tight text-gray-700 shadow focus:outline-none"
            id="email"
            type="email"
            v-model="form.email"
            placeholder="Enter your email"
            required />
        </div>
        <div class="mb-6 mt-6 w-full">
          <label class="mb-2 block text-accent-blue-700" for="message">
            Message
            <span class="text-danger-500">*</span>
          </label>
          <textarea
            class="focus:shadow-outline w-full appearance-none rounded border px-3 py-2 leading-tight text-gray-700 shadow focus:outline-none"
            id="message"
            rows="5"
            v-model="form.message"
            placeholder="Enter your message"
            required></textarea>
        </div>
        <div class="flex items-center justify-center">
          <button
            @click.prevent="submitForm"
            class="focus:shadow-outline rounded-xl bg-blue-500 px-12 py-2 font-bold text-white hover:bg-blue-700 focus:outline-none">
            Submit
          </button>
        </div>
      </form>
    </div>
    <div v-else>
      <div class="bg-white px-24 py-16 border">
        <div class="flex items-center">
          <svg
            class="h-12 w-12 text-green-500 md:ml-4"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor">
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M5 13l4 4L19 7"></path>
          </svg>
          <h2 class="ml-4 text-2xl font-bold text-gray-800">
            Question Sent Successfully
          </h2>
        </div>
        <div class="mt-8 text-lg leading-10 text-gray-600">
          <p>
            Thank you for submitting your question. Our team will review your
            message and contact you as soon as possible.
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { reactive, ref, Ref } from 'vue';
import PhoneImg from '@/assets/jpg/phone.jpg';

// import { useEmailStore } from '@/stores/email';
// const { contactUs } = useEmailStore();

const mode: Ref<'form' | 'result'> = ref('form' as 'form' | 'result');

const form = reactive({
  name: '',
  email: '',
  message: '',
});

async function submitForm() {
  try {
    // await contactUs(form.message, form.email, form.name);
    mode.value = 'result';
  } catch (e) {
    console.error(e);
  }
}
</script>

<style lang="scss">
img {
  object-position: 30% center;
}
input {
  @media (max-width: 768px) {
    width: min(75vw, 500px);
  }
}

/* CONTACT */
.contact {
  position: relative;
  width: 100%;
  margin-top: 50px;
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
}

.contact-form {
  position: relative;
  background: #f9f9f9;
  width: calc(100% - 400px);
  padding: 60px 40px 20px;
}

.contact-form form {
  width: 100%;
}

.contact-form .row {
  width: 100%;
  display: flex;
}

.contact-form .input50 {
  width: 50%;
  margin: 0 10px;
}

.contact-form .input100 {
  width: 100%;
  margin: 0 10px;
}

.contact-form .row input,
.contact-form .row textarea {
  position: relative;
  border: 1px solid rgba(0, 0, 0, 0.2);
  color: #111;
  background: transparent;
  width: 100%;
  padding: 10px;
  outline: none;
  font-size: 16px;
  font-weight: 300;
  margin: 10px 0;
  resize: none;
}

.contact-form .row textarea {
  height: 150px;
}

.contact-form .row input[type='submit'] {
  background-color: var(--secondary-color);
  color: #fff;
  margin: 0;
  text-transform: uppercase;
  letter-spacing: 2px;
  font-weight: 300;
  border: 0;
  cursor: pointer;
}

.contact-info {
  width: 350px;
  background: #f9f9f9;
  padding: 60px 40px 20px;
}

.contact-info .info-box {
  display: flex;
  align-items: flex-start;
  margin-bottom: 40px;
}

.contact-info .info-box .contact-icon {
  width: 20px;
  margin-right: 40px;
}

.contact-info .info-box .details h4 {
  color: var(--secondary-color);
}

.contact-info .info-box .details p,
.contact-info .info-box .details a {
  color: #111;
}
</style>
