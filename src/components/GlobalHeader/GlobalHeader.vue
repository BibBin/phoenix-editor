<template>
  <nav class="navbar navbar-dark bg-primary justify-content-between mb-4 nav-container">
    <a class="navbar-brand" href="#">1号湾岸</a>
    <ul v-if="!user.isLogin" class="list-inline mb-0">
      <li class="list-inline-item">
        <a href="#" class="btn btn-outline-light">登录</a>
      </li>
      <li class="list-inline-item">
        <a href="#" class="btn btn-outline-light"> 注册</a>
      </li>
    </ul>
    <ul v-else class="list-inline mb-0">
      <li class="list-inline-item">
        <dropdown :title="`hello ${user.name}`" />
      </li>
    </ul>
  </nav>
</template>
<script lang="ts">
import {defineComponent, PropType} from 'vue'
import Dropdown from '../Dropdown/Dropdown.vue'
export interface UserProps {
  isLogin: boolean;
  name?:string;
  id?:number;
}
export default defineComponent({
  name: "GolbalHeader",
  props: {
    user: {
      type: Object as PropType<UserProps>,
      require: true
    }
  },
  components: {
    Dropdown
  }
})
</script>
<style lang="less" scoped>
.nav-container{
  padding-right:20px;
  padding-left:20px;
}
</style>