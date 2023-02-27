<script lang="ts">
import { ref, onMounted } from 'vue'

export default {
    setup() {
        const remainingTime = ref<number>(60)

        const startTimer = () => {
            setInterval(() => {
                remainingTime.value--
            }, 1000)
        }

        onMounted(() => {
            startTimer()
        })

        return {
            remainingTime
        }
    }
}
</script>

<template>
    <div class="timer">
        <h1>{{ remainingTime }}</h1>
    </div>
</template>