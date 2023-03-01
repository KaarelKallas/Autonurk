<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue'
import { Head, useForm } from '@inertiajs/vue3'

const form = useForm({
    make: null,
    model: null,
    images: null
})


</script>

<template>
    <Head title="Dashboard" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">Dashboard</h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6 text-gray-900">You're logged in!</div>
                </div>
                <form @submit.prevent="form.post('/cars/store')">
                    <label for="make">Make:</label>
                    <input id="make" v-model="form.make" />
                    <label for="model">Model:</label>
                    <input id="model" v-model="form.model" />
                    <label for="images">Images:</label>
                    <progress v-if="form.progress" :value="form.progress.percentage" max="100">
                        {{ form.progress.percentage }}%
                    </progress>

                    <div class="flex items-center text-center">
                        <input type="file" name="images[]" multiple @input="form.images = $event.target.files" />
                    </div>

                    <button type="submit">Submit</button>
                </form>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
