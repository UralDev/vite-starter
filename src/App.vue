<template>
    <div class="w-[200px] mx-auto">
        <ul class="flex my-2">
            <li class="mr-3">
                <router-link class="text-green-700 hover:text-green-900" :to="{name: 'Home'}">Home</router-link>
            </li>
            <li>
                <router-link class="text-green-700 hover:text-green-900" :to="{name: 'About'}">About</router-link>
            </li>
        </ul>
        <router-view />
    </div>
</template>
