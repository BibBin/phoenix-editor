<template>
  <div id="nav">
    <Suspense>
      <template #default>
        <div>
          <async-show />
          <dog-show />
        </div>
      </template>
      <template #fallback>
        <h1>Loading!...</h1>
      </template>
    </Suspense>
  </div>
</template>
<script lang="ts">
import { defineComponent } from 'vue';
import AsyncShow from '@/components/AsyncShow/AsyncShow.vue'
import DogShow from '@/components/AsyncShow/DogShow.vue'
export default defineComponent({
  name: 'Home',
  components: {
    AsyncShow,
    DogShow,
  }
});
</script>
