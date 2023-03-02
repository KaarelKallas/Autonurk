<script setup>
import { Head, Link } from '@inertiajs/vue3';


const props = defineProps({
    cars: {
        type: Object,
        default: () => ({}),
    },
    images: {
        type: Object,
        default: () => ({}),
    },
})
console.log(props.images)
console.log(props.cars)

</script>
<script>
import Layout from "../Layouts/Layout.vue";
export default {
    layout: Layout
}
</script>
<template>

    <div v-for="car in cars">
        <div v-for="image in images">
            <img :src="'/storage/' + image.order_column + '/' + image.file_name" alt="">
        </div>
    </div>

</template>
