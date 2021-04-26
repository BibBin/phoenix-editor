<template>
  <div @click="updateDt">
    watch document title
  </div>
</template>
<script lang="ts">
// 定义响应式变量，响应式对象
import {defineComponent, ref, watch, reactive, computed  } from 'vue'
interface DataProps {
  count: number;
  double: number;
  increase: () => void;
}
export default defineComponent({
  name: 'crease',
  setup(){
   const dt = ref('')
   const data:DataProps = reactive({
      count:0,
      increase: ()=> {data.count++},
      double: computed(()=>  data.count*2)
    })
   const updateDt = () => {
     dt.value += 'Hello'
     data.count+=1
   }
   // 监听单个
  //  watch(dt, (newValue, oldValue)=> {
  //    console.log('new',newValue)
  //    console.log('old',oldValue)
  //    document.title = dt.value
  //  })


  // 监听多个
   watch([dt, ()=> data.count], (newValue, oldValue)=> {
     console.log('new',newValue)
     console.log('old',oldValue)
     document.title = dt.value
   })
    return {
      dt,
      updateDt
    }
  }
})
</script>
