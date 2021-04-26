<template>
  <div id="nav">
    <component :is="currentId" />
  </div>
</template>
<script lang="ts">
import { defineComponent } from 'vue';
import demo1 from '@/demos/ls_1_ref_reactive_toRefs.vue'; 
import demo2 from '@/demos/ls_2_life_cycle.vue'; 
import demo3 from '@/demos/ls_3_watch.vue'; 
import demo4 from '@/demos/ls_4_catch_mouse_position.vue'; 
import demo5 from '@/demos/ls_5_url_loader.vue'; 
import demo6 from '@/demos/ls_6_modal_use_teleport.vue'; 
import demo7 from '@/demos/ls_7_async_show_use_suspense.vue'; 
import demo8 from '@/demos/ls_8_cloumn_list.vue'
import demo9 from '@/demos/ls_9_dropdown_use_click_outside.vue'
export default defineComponent({
  name: 'Home',
  components: {
    demo1,
    demo2,
    demo3,
    demo4,
    demo5,
    demo6,
    demo7,
    demo8,
    demo9
  },
  setup() {
    return {
      currentId: 'demo8'
    }
  }
});
</script>
<style lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
