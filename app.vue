<template>

  <Link rel="icon" type="image/png" href="/squaredskwb.svg" />
  <Title>SKWB :: ☆</Title>

  <UApp :toaster="{
    class: 'left-0 *:right-0 *:bottom-0 *:p-2 *:bg-[#11111b] *:border-2 *:hover:border-[#45475a] *:border-[#313244] *:flex *:items-center *:gap-2 *:text-[#fff]',
  }">
    <div class="flex md:flex-row overflow-auto md:mt-0 mt-8 flex-col gap-4 w-11/12">
      <div class="flex flex-col gap-4 md:w-3/12 w-full md:sticky md:top-0 md:self-start h-fit">
        <div class="flex flex-col -space-y-3">
          <button @click="toggleSiteMap" class="flex items-center gap-1 z-10 bg-[#11111b] px-2 w-fit ml-4">
            <Icon name="mdi:chevron-right" class="transition-transform duration-200 ease-in-out"
              :class="{ 'rotate-90': isSiteMapOpen }" />
            Site map
          </button>
          <div class="container">
            <Tree v-if="isSiteMapOpen" :items="pages" />
          </div>
        </div>
        <div class="flex flex-col -space-y-3">
          <button @click="toggleSocials" class="flex items-center gap-1 z-10 bg-[#11111b] px-2 w-fit ml-4">
            <Icon name="mdi:chevron-right" class="transition-transform duration-200 ease-in-out"
              :class="{ 'rotate-90': isSocialsOpen }" />
            The socials
          </button>
          <div class="container">
            <Tree v-if="isSocialsOpen" :items="social" />
          </div>
        </div>
      </div>
      <div class="flex flex-col w-full -space-y-3">
        <button class="flex items-center gap-1 z-10 bg-[#11111b] w-fit ml-4 px-2 ">
          SKWB
        </button>
        <div class="container w-full">
          <NuxtPage />
        </div>
      </div>
    </div>

  </UApp>
</template>

<script setup lang="ts">
import { useMediaQuery } from '@vueuse/core';
const isMd = useMediaQuery('(min-width: 768px)');

const isSiteMapOpen = ref(!isMd.value);
const isSocialsOpen = ref(!isMd.value);

isMd.valueChanged(() => {
  if (isMd.value) {
    isSiteMapOpen.value = false;
    isSocialsOpen.value = false;
  } else {
    isSiteMapOpen.value = true;
    isSocialsOpen.value = true;
  }
});

const toggleSiteMap = () => {
  isSiteMapOpen.value = !isSiteMapOpen.value;
};

const toggleSocials = () => {
  isSocialsOpen.value = !isSocialsOpen.value;
};

const pages = [
  { icon: 'mdi:home', name: 'Home', link: '/' },
  { icon: 'material-symbols:person-book', name: 'Characters', link: '/characters' },
  { icon: 'material-symbols:newspaper', name: 'Blog', link: '/blog' },
  { icon: 'material-symbols:code', name: 'Projects', link: '/projects' },
  {
    icon: 'maki:museum',
    name: 'Museum',
    link: '/museum',
    children: [
      { icon: 'mdi:palette', name: 'Drawings', link: '/drawings' },
      { icon: 'material-symbols:music-note', name: 'Musics', link: '/musics' },
    ],
  },
  {
    icon: 'material-symbols:groups',
    name: 'Members',
    link: '/members',
    children: [
      { icon: 'game-icons:goat', name: 'Skiqq', link: '/members/skiqq' },
      { icon: 'material-symbols:add', name: 'Join', link: '/members/how2join' },
    ],
  },
];

const social = [
  { icon: 'material-symbols:planet', name: 'Source code', link: 'https://github.com/skiqq-flower/skwb.website' },
  { icon: 'carbon:logo-x', name: 'X/Twitter', link: 'https://x.com/skwb_hq' },
  { icon: 'mdi:instagram', name: 'Instagram', link: 'https://www.instagram.com/skwb.hq' },
  { icon: 'ic:baseline-discord', name: 'Discord', link: 'https://discord.gg/TAfgTxjDxM' },
  { icon: 'ic:baseline-telegram', name: 'Telegram', link: 'https://t.me/skwb_hq' },
  { icon: 'mdi:rss', name: 'RSS', link: '/blog/rss' },
];
</script>
