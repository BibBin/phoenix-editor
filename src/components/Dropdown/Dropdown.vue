<template>
  <div class="dropdown" ref="dropdownRef">
    <a href="#" class="btn btn-outline-light" @click.prevent="toggleOpen">{{title}}</a>
    <ul class="dropdown-menu" :style="{display: 'block'}" v-show="isOpen">
      <li class="dropdown-item">
        <a href="#">新建文章</a>
      </li>
      <li class="dropdown-item">
        <a href="#">编辑资料</a>
      </li>
    </ul>
  </div>
</template>
<script lang="ts">
import {defineComponent,ref, watch} from 'vue'
import useClickOutside from '@/hooks/useClickOutside'
export default defineComponent({
  name: 'Dropdown',
  props: {
    title: {
      type: String,
      require: true
    }
  },
  setup(){
    const isOpen = ref(false)
    const dropdownRef = ref<null | HTMLElement>(null)
    const toggleOpen = () => {
      isOpen.value = !isOpen.value
    }
    const isClickOutside = useClickOutside(dropdownRef)
    watch(isClickOutside, () => {
      if(isClickOutside.value && isOpen.value){
          isOpen.value = true
        }else{
          isOpen.value = false
        }
    })
    return {
      isOpen,
      toggleOpen,
      dropdownRef
    }
  }
})
</script>