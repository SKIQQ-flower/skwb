<template>
  <Link rel='icon' type='image/png' href='/squaredskwb.svg' />
  <Title>SKWB :: ☆</Title>
  <UApp :toaster="{
    class: 'left-0 *:right-0 *:bottom-0 *:p-2 *:bg-[#11111b] *:border-2 *:hover:border-[#45475a] *:border-[#313244] *:flex *:items-center *:gap-2 *:text-[#fff]',
  }">
    <div class="flex md:flex-row flex-col h-fit gap-4 w-11/12 md:h-11/12">
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
    name: 'Facts',
    link: '/facts',
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
  {
    icon: 'material-symbols:groups',
    name: 'Members',
    link: '/members',
    children: [
      {
        icon: 'game-icons:goat',
        name: 'Skiqq',
        link: '/members/skiqq',
      },
      {
        icon: 'material-symbols:add',
        name: 'Join',
        link: '/members/how2join',
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
    icon: 'carbon:logo-x',
    name: 'X/Twitter',
    link: 'https://x.com/skwb_hq',
  },
  {
    icon: 'mdi:instagram',
    name: 'Instagram',
    link: 'https://www.instagram.com/skwb.hq',
  },
  {
    icon: 'ic:baseline-discord',
    name: 'Discord',
    link: 'https://discord.gg/TAfgTxjDxM',
  },
  {
    icon: 'ic:baseline-telegram',
    name: 'Telegram',
    link: 'https://t.me/skwb_hq',
  },
  {
    icon: 'mdi:rss',
    name: 'RSS',
    link: '/blog/rss',
  }
]
</script>