<script setup>
import { Head, Link, useForm } from '@inertiajs/vue3';

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
function getImages(id, image) {
    let imagesById = []
    if (image.model_id == id) {
        imagesById.push('/storage/' + image.id + '/' + image.file_name)
    }
    console.log(imagesById)
    return imagesById
}
const formDelete = useForm({})
function destroy(id) {
    if (confirm('Are you sure you want to Delete')) {
        formDelete.delete(route('cars.destroy', id))
    }
}

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

    <div class="text-white" v-for="car in cars">
        <span>{{ car.make }}</span>
        <span>{{ car.model }}</span>
        <div v-for="image in images" class="flex w-[10vw]">
            <img :src="getImages(car.id, image)">
        </div>
        <button @click="destroy(car.id)">DELETE</button>
    </div>

</template>
