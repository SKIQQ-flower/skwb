<template>
    <img class="border-2 p-2 hover:border-[#45475a] border-[#313244]" src="/skwbtext.svg">
    <h1 class="title">Greetings, this is SKWB!</h1>
    <p>Hello, welcome to SKWB website, the heart of our company. Check the projects, social medias, blog and other pages
        made with &lt;3</p>
    <h2 class="title mt-4">About</h2>
    <p>SKWB is a hub for creative content, we aim to create online media, such as comics, drawings, musics, games and so
        forth.</p>
    <h2 class="title mt-4">Learn more with our pages</h2>
    <div class="flex md:flex-row md:flex-wrap flex-col h-fit gap-4 md:w-11/12 md:items-start items-center w-full">
        <div class="hover:border-[#45475a] border-2 p-2 w-fit flex flex-col border-[#313244]">
            <img src="/bodedope_pfp.png" class="size-56">
            <p class="text-xl font-bold font-mono">Bodedope</p>
            <p class="w-56">One of our characters, a lovely goat filled with emotions.</p>
            <NuxtLink to="/characters"
                class="border-[#313244] hover:border-[#45475a] mt-2 border-2 flex flex-row items-center">
                <Icon name="mdi:chevron-right" /> See all characters
            </NuxtLink>
        </div>
        <div class="hover:border-[#45475a] border-2 p-2 w-fit flex flex-col border-[#313244]">
            <img src="/epnoia_pfp.png" class="size-56">
            <p class="text-xl font-bold font-mono">Epnoia</p>
            <p class="w-56">Our first game, yet in development.</p>
            <NuxtLink to="/projects"
                class="border-[#313244] hover:border-[#45475a] mt-2 border-2 px-2 flex flex-row items-center">
                <Icon name="mdi:chevron-right" /> Check out our projects
            </NuxtLink>
        </div>
        <div class="hover:border-[#45475a] border-2 p-2 w-fit flex flex-col border-[#313244]">
            <Icon name="material-symbols:newspaper" class="size-56" />
            <p class="text-xl font-bold font-mono">What we are doing?</p>
            <p class="w-56">You can check the blog for updates.</p>
            <NuxtLink to="/blog"
                class="border-[#313244] hover:border-[#45475a] mt-2 border-2 px-2 flex flex-row items-center">
                <Icon name="mdi:chevron-right" /> Visit our blog
            </NuxtLink>
        </div>
        <div class="hover:border-[#45475a] border-2 p-2 w-fit flex flex-col border-[#313244]">
            <Icon name="maki:museum" class="size-56" />
            <p class="text-xl font-bold font-mono">The SKWB museum</p>
            <p class="w-56">Drawings and Music, a museum that is open 24/7.</p>
            <NuxtLink to="/museum"
                class="border-[#313244] hover:border-[#45475a] mt-2 border-2 px-2 flex flex-row items-center">
                <Icon name="mdi:chevron-right" /> Have fun in museum
            </NuxtLink>
        </div>
        <div class="hover:border-[#45475a] border-2 p-2 w-fit flex flex-col border-[#313244]">
            <Icon name="material-symbols:groups" class="size-56" />
            <p class="text-xl font-bold font-mono">All members</p>
            <p class="w-56">Come see the members of SKWB (you can be one too!)</p>
            <NuxtLink to="/characters/bodedope"
                class="border-[#313244] hover:border-[#45475a] mt-2 border-2 px-2 flex flex-row items-center">
                <Icon name="mdi:chevron-right" /> Check the members
            </NuxtLink>
        </div>
    </div>
</template>