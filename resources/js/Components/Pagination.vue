
<script setup>
import { Link } from "@inertiajs/inertia-vue3";

const props = defineProps({
    links:Object
})
</script>

<template >
<div v-for="(link, index) of props.links" :key="index">
        <div v-if="link.url == null" v-html="link.label"></div>
    <Link
        v-else
        :href="link.url"
        v-html="link.label"
        class="p-1 m-1"
        :class="{ 'bg-gray-400': link.active }"
    ></Link>
</div>

</template>
