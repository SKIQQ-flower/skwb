<template>
    <ul class="tree">
        <li v-for="(item, idx) in items" :key="idx">
            <NuxtLink v-if="item.link" :href="item.link" class="flex items-center gap hover:bg-[#313244]">
                <Icon class="text-lg" v-if="item.icon" :name="item.icon" />
                {{ item.name }}
                <span v-if="item.description" class="text-xs font-mono text-gray-400 flex flex-row">
                    <p class="text-xs">//</p>
                    <p class="text-xs">({{ item.description }})</p>
                </span>
            </NuxtLink>
            <p v-else-if="!item.handle"
                class="flex items-center gap px-2 py-1 bg-[#1e1e2e]/50 text-xs font-semibold text-gray-300">
                <Icon class="text-lg opacity-70" v-if="item.icon" :name="item.icon" />
                {{ item.name }}
                <span v-if="item.description"
                    class="ml-1 text-xs font-mono text-gray-400 flex flex-row items-center gap-1">
                    <span class="text-xs">//</span>
                    <span>({{ item.description }})</span>
                </span>
            </p>
            <p v-else class="flex items-center gap hover:bg-[#313244]" @click="copyToClipboard(item.handle)">
                <Icon class="text-lg" v-if="item.icon" :name="item.icon" />
                {{ item.name }}
                <span v-if="item.description" class="text-xs font-mono text-gray-400 flex flex-row">
                    <p class="text-xs">//</p>
                    <p class="text-xs">({{ item.description }})</p>
                </span>
            </p>
            <ul v-if="item.children">
                <Tree :items="item.children" />
            </ul>
        </li>
    </ul>
</template>

<script setup>
const { copy } = useClipboard()
const toast = useToast()
const props = defineProps({
    items: { type: Array, required: true }
})

function copyToClipboard(item) {
    copy(item.handle)
    toast.add({
        title: 'Copied to clipboard',
    })
}
</script>

<style scoped>
ul {
    list-style: none;
}

.tree a,
.tree p {
    padding: 4px;
}

.tree {
    padding-left: 0;
    margin: 0;
    list-style: none;
    position: relative;
}

.tree ul {
    margin: 0;
    padding-left: 0.25em;
    list-style: none;
    position: relative;
}

.tree li {
    margin: 0;
    padding: 0.25em 1.5em;
    position: relative;
    display: block;
    white-space: pre;
    cursor: default;
}

.tree li::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    border-left: 2px solid #313244;
}

.tree li>a::before,
.tree li>p::before {
    content: '';
    position: absolute;
    top: 0.9em;
    left: 0em;
    width: 1.25em;
    border-top: 2px solid #313244;
}

.tree li:last-child::before {
    height: 0.9em;
}
</style>
