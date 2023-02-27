<script lang="ts">
import { ref } from 'vue'

export default {
    data() {
        const remainingTime = ref<number>(10)

        const startTimer = () => {
            setInterval(() => {
                remainingTime.value--
            }, 1000)
        }

        const resetTimer = () => {
            remainingTime.value = 10
        }

        return {
            remainingTime,
            startTimer,
            resetTimer,
        }
    }
}
</script>

<template>
    <div class="timer">
        <h1>{{ remainingTime }}</h1>
        <button @click="startTimer">Start</button>
        <button @click="resetTimer">Reset</button>
    </div>
</template>