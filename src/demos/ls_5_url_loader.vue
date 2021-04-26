<template>
  <div>
    <h1 v-if="loading">Loading</h1>
    <img v-if="loaded" :src="result.message" alt="">
  </div>
</template>
<script lang="ts">
import {defineComponent, watch  } from 'vue'
import useURLLoader from '@/hooks/useURLLoader'
interface DogResult {
  message: string;
  status: string;
}
export default defineComponent({
  name: 'crease',
  setup(){
    const {result,loading,loaded} = useURLLoader<DogResult>('https://dog.ceo/api/breeds/image/random')
    watch(result, ()=>{
      if(result.value){
        // 不添加[DogResult]会报错
        console.log(result.value.message)
      }
    })
    return {
      result,
      loading,
      loaded
    }
  }
})
</script>
