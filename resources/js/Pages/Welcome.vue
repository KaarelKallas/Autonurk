<script setup>
import { Head, Link } from '@inertiajs/vue3';

defineProps({
    canLogin: Boolean,
    canRegister: Boolean,
    laravelVersion: String,
    phpVersion: String,
});
</script>
<script>
import Layout from "../Layouts/Layout.vue";
export default {
    layout: Layout
}
</script>
<template>

</template>
