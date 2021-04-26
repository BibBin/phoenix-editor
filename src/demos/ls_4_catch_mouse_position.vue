<template>
  <div @click="updateMouse">
    x:{{x}}y:{{y}}
  </div>
</template>
<script lang="ts">
// 定义响应式变量，响应式对象
import {defineComponent, ref, onMounted, onUnmounted  } from 'vue'
import useMousePosition from '@/hooks/useMousePosition'
export default defineComponent({
  name: 'crease',
  setup(){
  //  const x = ref(0)
  //  const y = ref(0)
  //  const updateMouse = (e:MouseEvent)=>{
  //    x.value =e.pageX
  //    y.value =e.pageY
  //  }
  //  onMounted(()=>{
  //    document.addEventListener('click',updateMouse)
  //  })
  //  onUnmounted(()=>{
  //    document.removeEventListener('click',updateMouse)
  //  })
   const {x,y} = useMousePosition()
    return {
      x,
      y
    }
  }
})
</script>
