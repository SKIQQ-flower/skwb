<template>
  <Title>SKWB :: ☆</Title>
  <UApp :toaster="{
    class: 'left-0 *:right-0 *:bottom-0 *:p-2 *:bg-[#11111b] *:border-2 *:hover:border-[#45475a] *:border-[#313244] *:flex *:items-center *:gap-2 *:text-[#fff]',
  }">
    <div class="flex md:flex-row flex-col h-fit gap-2 w-11/12 md:h-11/12">
      <div class="flex flex-col h-full gap-4">
        <div class="container relative h-full">
          <h1 class="px-2 bg-[#11111b] absolute -top-4">Site map</h1>
          <Tree :items="pages" />
        </div>
        <div class="container relative h-full">
          <h1 class="px-2 bg-[#11111b] absolute -top-4">The socials</h1>
          <Tree :items="social" />
        </div>
      </div>
      <div class="container relative">
        <h1 class="px-2 bg-[#11111b] absolute -top-4">SKWB</h1>
        <NuxtPage />
      </div>
    </div>
  </UApp>
</template>

<script setup lang="ts">

const pages = [
  {
    icon: 'mdi:home',
    name: 'Home',
    link: '/',
  },
  {
    icon: 'material-symbols:person-book',
    name: 'Characters',
    link: '/characters',
  },
  {
    icon: 'material-symbols:newspaper',
    name: 'Blog',
    link: '/blog',
  },
  {
    icon: 'material-symbols:question-mark',
    name: 'FAQ',
    link: '/blog',
  },
  {
    icon: 'maki:museum',
    name: 'Museum',
    link: '/museum',
    children: [
      {
        icon: 'mdi:palette',
        name: 'Drawings',
        link: '/drawings',
      },
      {
        icon: 'material-symbols:music-note',
        name: 'Musics',
        link: '/musics',
      }
    ],
  },
]

const social = [
  {
    icon: 'material-symbols:planet',
    name: 'Source code',
    link: 'https://github.com/SKWB-gh/skwb.website',
  },
  {
    icon: 'mdi:github',
    name: 'GitHub',
    link: 'https://github.com/SKIQQ-flower',
  },
  {
    icon: 'mdi:twitter',
    name: 'Twitter',
    link: 'https://twitter.com/SKIQQ_',
  },
  {
    icon: 'mdi:instagram',
    name: 'Instagram',
    link: 'https://www.instagram.com/skwb.art',
  },
  {
    icon: 'ic:baseline-discord',
    name: 'Discord',
    handle: '@skiqq'
  },
  {
    icon: 'mdi:rss',
    name: 'RSS',
    link: '/blog/rss',
  }
]
</script>