<script setup lang="ts">
import { Head, Link } from '@inertiajs/vue3';
import AppLogo from '@/components/AppLogo.vue';
</script>

<template>
    <Head title="Welcome" />
    <div class="dark:bg-linear-to-b min-h-screen bg-white antialiased dark:from-neutral-950 dark:to-neutral-900">
        <header class="not-has-[nav]:hidden mb-6 w-full text-sm lg:mx-auto lg:max-w-4xl">
            <nav class="flex items-center justify-between gap-4 p-6 lg:justify-end">
                <Link
                    v-if="$page.props.auth.user"
                    :href="route('dashboard')"
                    class="inline-block rounded-sm border border-[#19140035] px-5 py-1.5 text-sm leading-normal text-[#1b1b18] hover:border-[#1915014a] dark:border-[#3E3E3A] dark:text-[#EDEDEC] dark:hover:border-[#62605b]">
                    Dashboard
                </Link>
                <template v-else>
                    <Link
                        :href="route('login')"
                        class="inline-block rounded-sm border border-transparent px-5 py-1.5 text-sm leading-normal text-[#1b1b18] hover:border-[#19140035] dark:text-[#EDEDEC] dark:hover:border-[#3E3E3A]">
                        Log in
                    </Link>
                    <Link
                        :href="route('register')"
                        class="inline-block rounded-sm border border-[#19140035] px-5 py-1.5 text-sm leading-normal text-[#1b1b18] hover:border-[#1915014a] dark:border-[#3E3E3A] dark:text-[#EDEDEC] dark:hover:border-[#62605b]">
                        Register
                    </Link>
                </template>
            </nav>
        </header>
        <div
            class="duration-250 starting:opacity-0 flex w-full items-center justify-center opacity-100 transition-opacity lg:grow">
            <main class="flex flex-col items-center justify-between">
                <AppLogo class="mb-8 w-48" />
                <h3 class="text-xl">{{ $page.props.app.name }}</h3>
            </main>
        </div>
        <div class="h-14.5 hidden lg:block"></div>
    </div>
</template>
