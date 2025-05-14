<template>
    <img class="border-2 p-2 hover:border-[#45475a] border-[#313244]" src="/skwbtext.svg">
    <h1 class="title">Greetings, this is SKWB!</h1>
    <p>Hello, welcome to SKWB website, the heart of our company. Check the projects, social medias, blog and other pages
        made with &lt;3</p>
    <h2 class="title mt-4">About</h2>
    <p>SKWB is a hub for creative content, we aim to create online media, such as comics, drawings, musics, games and so
        forth.</p>
    <h2 class="title mt-4">Learn more with our pages</h2>
    <div class="flex md:flex-row flex-col h-fit gap-4 w-11/12">
        <div class="hover:border-[#45475a] border-2 p-2 w-56 flex flex-col border-[#313244]">
            <img src="/bodedope_pfp.png" class="size-56">
            <p class="text-xl font-bold font-mono">Bodedope</p>
            <p>One of our characters, a lovely goat filled with emotions.</p>
            <NuxtLink to="/characters/bodedope"
                class="border-[#313244] hover:border-[#45475a] mt-2 border-2 flex flex-row items-center">
                <Icon name="mdi:chevron-right" /> See all characters
            </NuxtLink>
        </div>
    </div>
</template>