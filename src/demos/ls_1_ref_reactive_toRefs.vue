<template>
  <div>
   <h1>{{countSingle}}</h1>
   <h1>{{doubleSingle}}</h1>
   <button @click="increaseSingle">+1</button>
   <h1>{{count}}</h1>
   <h1>{{double}}</h1>
   <button @click="increase">+1</button>
  </div>
</template>
<script lang="ts">
// 定义响应式变量，响应式对象
import {defineComponent, ref, computed, reactive, toRefs } from 'vue'
interface DataProps {
  count: number;
  double: number;
  increase: () => void;
}
export default defineComponent({
  name: 'crease',
  setup(props){
    console.log(props)
    // 使用ref
    const countSingle = ref(0)
    const doubleSingle = computed(()=> {
      return countSingle.value*2
    })
    const increaseSingle = () => {
      return countSingle.value++
    }

    // 使用响应式对象【reactive】
    const data:DataProps = reactive({
      count:0,
      increase: ()=> {data.count++},
      double: computed(()=>  data.count*2)
    })
    // 反应对象转换为普通对象，其中所得对象的每个属性都ref指向原始对象的相应属性。 这样解构赋值[...refData]展开的每一项才是响应式对象
    const refData = toRefs(data)
    return {
      countSingle,
      doubleSingle,
      increaseSingle,
      ...refData
    }
  }
})
</script>
