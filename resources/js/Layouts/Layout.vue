<script setup>
import { ref } from 'vue'
import ApplicationLogo from '@/Components/ApplicationLogo.vue'
import Dropdown from '@/Components/Dropdown.vue'
import DropdownLink from '@/Components/DropdownLink.vue'
import NavLink from '@/Components/NavLink.vue'
import ResponsiveNavLink from '@/Components/ResponsiveNavLink.vue'
import { Link } from '@inertiajs/vue3'

const showingNavigationDropdown = ref(false)
</script>

<template>
    <div>
        <div class="min-h-screen bg-gradient-to-b from-[#505A5B] to-[#9BA0A0]">
            <nav class="bg-[#505A5B] border-b-[3px] border-[#ED9B40] drop-shadow-nav">
                <!-- Primary Navigation Menu -->
                <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                    <div class="flex justify-between h-32">
                        <div class="flex">
                            <!-- Logo -->
                            <div class="shrink-0 flex items-center ">
                                <Link :href="route('home')">
                                    <ApplicationLogo
                                        class="block w-auto fill-current text-gray-800"
                                    />
                                </Link>
                            </div>

                            <!-- Navigation Links -->
                            <div class="hidden space-x-8 sm:-my-px sm:ml-10 sm:flex text-white justify-center items-center">
                                <NavLink :href="route('dashboard')" :active="route().current('dashboard')">
                                    Uued sõidukid
                                </NavLink>
                                <NavLink :href="route('cars.index')" :active="route().current('cars.index')">
                                    Kasutatud sõidukid
                                </NavLink>
                                <NavLink :href="route('dashboard')" :active="route().current('dashboard')">
                                    Teenused
                                </NavLink>
                                <div class="flex flex-col items-end pb-4">
                                    <NavLink :href="route('dashboard')" :active="route().current('dashboard')">
                                        Kuidas meie teenus töötab?
                                    </NavLink>

                                    <div class="flex space-x-8 pt-3">
                                        <NavLink :href="route('dashboard')" :active="route().current('dashboard')">
                                            Kontakt
                                        </NavLink>
                                        <NavLink :href="route('dashboard')" :active="route().current('dashboard')">
                                            KKK
                                        </NavLink>
                                    </div>
                                </div>

                            </div>
                        </div>

                        <div class="hidden sm:flex sm:items-center sm:ml-6">
                            <!-- Settings Dropdown -->
                        </div>

                        <!-- Hamburger -->

                    </div>
                </div>
                <div class="border-[#ED9B40] border w-[136px] h-[34px] rounded-full flex items-center justify-center absolute right-[23vw] bottom-[-17px] bg-[#505A5B]">
                    <NavLink class="text-[#ED9B40]" :href="route('dashboard')" :active="route().current('dashboard')">
                        RateMyCar
                    </NavLink>
                </div>

            </nav>

            <!-- Page Heading -->
            <header class="bg-white shadow" v-if="$slots.header">
                <div class="max-w-7xl mx-auto py-6 px-4 sm:px-6 lg:px-8">
                    <slot name="header" />
                </div>
            </header>

            <!-- Page Content -->
            <main>
                <slot />
            </main>
        </div>
    </div>
</template>
