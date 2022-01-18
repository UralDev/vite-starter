<template>
    <div>
        <h1 class="text-3xl font-bold mb-4">Home Page</h1>
        <p class="mb-2">Name in store is: {{ name }}</p>
        <form @submit.prevent="saveName" class="flex items-center">
            <input v-model="newName" type="text" class="p-2 mr-1 border rounded" placeholder="Enter a new name">
            <button type="submit" class="p-2 text-white bg-indigo-600 rounded">Submit</button>
        </form>
    </div>
</template>

<script setup>
import { computed, ref } from 'vue'
import { useStore } from 'vuex'
import { useRouter } from 'vue-router'

const store = useStore()
const router = useRouter()

const name = computed(() => {
    return store.state.user.name
})

const newName = ref('')

function saveName() {
    store.dispatch('saveName', newName.value)
    newName.value = ''
    router.push({name: 'About'})
}
</script>