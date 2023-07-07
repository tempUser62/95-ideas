<template>
  <div class="flex w-screen flex-col items-center">
    <img src="@/assets/jpg/office.jpg" class="h-auto w-screen" />
    <div class="container mx-auto p-8 md:p-12">
      <h1 class="mb-6 text-center text-4xl font-bold">
        About {{ companyName }}
      </h1>
      <p class="text-lg text-gray-600">
        {{ companyName }} was founded in 2022, originating from the powerful
        fusion of creativity and technology. The narrative begins with two
        imaginative pioneers, Anton and Maksym. Having experienced firsthand the
        struggles of communication and creativity in the digital world, they
        took it upon themselves to craft a solution. Thus, {{ companyName }} was
        born.
        <br />
        <br />
        In the early days, we actively participated in industry
        discussions and collaborated with influential figures to plug gaps in
        the digital landscape. Their passion, coupled with cutting-edge
        technology, quickly turned heads. Government entities and businesses
        started recognizing {{ companyName }} for their transformative
        approaches, earning us trust and lasting partnerships.

        <br />
        <br />
        We believe in democratizing creativity and facilitating meaningful
        connections in the digital landscape. Our goal is to increase
        accessibility to creative digital solutions, allowing people to fully
        experience and contribute to the digital realm, all while ensuring their
        privacy and maintaining high standards of security.
      </p>
    </div>

    <div class="mt-8 md:pt-12 flex w-screen flex-col items-center bg-gray-50">
      <h2 class="mb-2 mt-6 text-center text-4xl font-bold text-accent-blue-800">
        Our Team
      </h2>
      <p class="mt-4 text-center">
        {{ companyName }} is composed of a talented ensemble of artists,
        writers, developers, and strategists.
      </p>

      <div
        class="md: mt-4 grid gap-4 p-4 p-8 sm:grid-cols-2 md:grid-cols-3 md:gap-8">
        <div
          v-for="person in teamMembers"
          :key="person.id"
          class="flex flex-col items-center rounded-3xl bg-white p-8 pb-8 shadow-xl">
          <img :src="person.image" :alt="person.name" class="h-auto w-screen" />
          <span class="mt-3 font-bold">{{ person.name }}</span>
          <span
            class="mt-4 min-w-[100px] rounded-2xl bg-gray-300 px-3 py-1 text-center font-bold">
            {{ person.position }}
          </span>
        </div>
      </div>
    </div>

    <div
      class="flex w-screen flex-col items-center p-8 md:pt-20 md:p-12 bg-gray-50">
      <h2 class="mb-2 mt-6 text-center text-4xl font-bold text-accent-blue-800">
        Our Mission
      </h2>
      <div class="mt-6 grid gap-4 md:grid-cols-3 md:gap-8">
        <div
          v-for="card in cards"
          :id="card.caption"
          class="shadow-xl shadow rounded-3xl p-8 flex flex-col items-center">
          <img :src="card.icon" class="h-16 w-16" />
          <span class="text-center mt-6 font-semibold">{{ card.caption }}</span>
        </div>
      </div>
    </div>

    <section
      class="flex w-screen flex-col items-center p-8 md:p-12 md:pt-16 bg-gray-50">
      <h2 class="mb-2 mt-6 text-center text-4xl font-bold text-accent-blue-800">
        Our Culture
      </h2>
      <div class="flex flex-col md:flex-row gap-4">
        <div
          class="md:w-1/2 flex justify-center md:self-center py-4 lg:px-8 xl:px-16 2xl:px-20 3xl:px-24 object-cover">
          <img src="@/assets/jpg/office-h.jpg" class="object-cover w-full" />
        </div>
        <div class="flex flex-col p-4 md:p-8 md:w-1/2">
          <div v-for="item in cultures" :id="item.title" class="mb-4">
            <h3 class="mt-4 text-2xl font-bold text-accent-blue-800">
              {{ item.title }}
            </h3>
            <p class="mt-4 text-gray-600 text-lg">{{ item.content }}</p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
import Face1 from '@/assets/jpg/team/face-1.jpg';
import Face2 from '@/assets/jpg/team/face-2.jpg';
import Face3 from '@/assets/jpg/team/face-3.jpg';
import Face4 from '@/assets/jpg/team/face-4.jpg';
import Face5 from '@/assets/jpg/team/face-5.jpg';
import Face6 from '@/assets/jpg/team/face-6.jpg';
import Face7 from '@/assets/jpg/team/face-7.jpg';
import Face8 from '@/assets/jpg/team/face-8.jpg';
import Face9 from '@/assets/jpg/team/face-9.jpg';
import Mission1 from '@/assets/png/mission-1.png';
import Mission2 from '@/assets/png/mission-2.png';
import Mission3 from '@/assets/png/mission-3.png';

const companyName = import.meta.env.VITE_COMPANY_NAME as string;
const companyShortName = import.meta.env.VITE_COMPANY_SHORT_NAME as string;

const teamMembers = [
  {
    id: 8,
    name: 'Ivan Tkachuk',
    position: 'Backend Developer',
    image: Face8,
  },
  {
    id: 9,
    name: 'Petro Kovalenko',
    position: 'UI/UX Designer',
    image: Face9,
  },
  {
    id: 7,
    name: 'Václav Raška',
    position: 'DevOps Engineer',
    image: Face7,
  },
  {
    id: 1,
    name: 'Maksymilian Kowalski',
    position: 'Tech Lead',
    image: Face1,
  },
  {
    id: 6,
    name: 'Maryla Wojciechowska',
    position: 'QA, Sales and Marketing',
    image: Face2,
  },
  {
    id: 3,
    name: 'Anton Lipskyi',
    position: 'Frontend Developer, CEO',
    image: Face3,
  },
];

const cards = [
  {
    caption: 'Democratize access to creative digital services',
    icon: Mission1,
  },
  {
    caption: 'Enable the next generation of digital services',
    icon: Mission2,
  },
  {
    caption: 'Empower creators to build the future',
    icon: Mission3,
  },
];

const cultures = [
  {
    title: 'Transparency',
    content:
      'We value open communication, where all actions and decisions are shared ' +
      'honestly and timely. We invite ideas and feedback from every member of our team and stakeholders.',
  },
  {
    title: 'Innovation',
    content:
      'Creativity and innovation are the pillars of our work. We recognize its ' +
      'importance in keeping us competitive and driving our growth. We`re always seeking' +
      ' new and improved ways to bring your ideas to life.',
  },
  {
    title: 'Integrity',
    content:
      'We uphold the highest levels of integrity in all that we do. We commit to adhering ' +
      'to ethical practices in all projects and relationships we build, holding ourselves ' +
      'accountable for our actions.',
  },
  {
    title: 'Teamwork',
    content:
      'We believe that together, ' +
      "we can achieve more. We foster a collaborative culture where every team member's" +
      ' contribution is valued and acknowledged. We encourage diversity of thought and ' +
      'respect for individual perspectives. ',
  },
  {
    title: 'Customer Focus',
    content:
      'Our clients are our priority. We strive to understand their needs, challenges, and ' +
      'aspirations, using this understanding to deliver tailored solutions that genuinely add value.',
  },
  {
    title: 'Passion',
    content:
      'Our passion drives us to exceed expectations, persist through challenges, and constantly evolve.' +
      " It's this passion that inspires us to learn, grow, and continually improve.",
  },
];
</script>

<style scoped lang="scss">
li {
  @apply mt-2;
}
</style>
