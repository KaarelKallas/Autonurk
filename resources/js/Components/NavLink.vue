<script setup>
import { computed } from 'vue';
import { Link } from '@inertiajs/vue3';

const props = defineProps(['href', 'active']);

const classes = computed(() =>
    props.active
        ? 'inline-flex items-center px-1 pt-1 border-b-2 border-indigo-400 text-xl font-bold leading-5 focus:outline-none focus:border-indigo-700 transition duration-150 ease-in-out font-outfit'
        : 'inline-flex items-center px-1 pt-1 border-b-2 border-transparent text-xl font-bold leading-5 hover:text-[#ED9B40] hover:border-[#ED9B40] focus:outline-none focus:text-[#ED9B40] focus:border-gray-300 transition duration-150 ease-in-out font-outfit'
);
</script>

<template>
    <Link :href="href" :class="classes">
        <slot />
    </Link>
</template>
