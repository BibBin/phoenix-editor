<template>
    <img :src="result&&result.message" alt="">
</template>
<script lang="ts">
import { defineComponent } from 'vue'
import useURLLoader from '@/hooks/useURLLoader'
interface DogResult {
  message: string;
  status: string;
}
export default defineComponent({
    async setup() {
        const {result} = await useURLLoader<DogResult>('https://dog.ceo/api/breeds/image/random')
        return {
            result
        }
    }
})
</script>