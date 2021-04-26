<template>
  <div>
    生命周期钩子
  </div>
</template>
<script lang="ts">
// 定义响应式变量，响应式对象
import {defineComponent, onActivated, onMounted, onRenderTriggered, onUnmounted, onUpdated,  } from 'vue'
export default defineComponent({
  name: 'crease',
  setup(){
    //加载
    onMounted(()=> {
      console.log('mounted')
    })
    // 更新
    onUpdated(()=>{
      console.log('onUpdated')
    })
    // 销毁
    onUnmounted(()=>{
      console.log('onUnmounted')
    })
    //激活
    onActivated(()=>{
      console.log('onActivated')
    })
    //新增的 [知道是什么导致了Vue实例中的重新渲染]
    onRenderTriggered((event)=> {
      console.log(event)
    })
    return {}
  }
})
</script>
