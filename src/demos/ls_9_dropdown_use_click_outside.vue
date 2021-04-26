<template>
    <global-header :user="currentUser" />
</template>
<script lang="ts">
import {defineComponent} from 'vue'
import GlobalHeader, { UserProps } from '@/components/GlobalHeader/GlobalHeader.vue'
const currentUser: UserProps = {
  isLogin:true,
  name: "瓦西里"
}
export default defineComponent({
  components: {
    GlobalHeader
  },
  setup(){
    return {
      currentUser
    }
  }
})
</script>
