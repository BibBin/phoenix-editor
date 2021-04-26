<template>
  <div id="nav">
    <div @click="openModal">Open Modal</div>
    <Modal :isOpend="modalIsOpen" @close-modal="onModalClose">My modal</Modal>
  </div>
</template>
<script lang="ts">
import { defineComponent,ref } from 'vue';
import Modal from '@/components/Modal/Modal.vue'
export default defineComponent({
  name: 'Home',
  components: {
    Modal,
  },
  setup(){
    const modalIsOpen = ref(false)
    const openModal = () => {
      modalIsOpen.value = true
    }
    const onModalClose = () => {
      modalIsOpen.value = false
    }
    openModal
    return {
      modalIsOpen,
      openModal,
      onModalClose
    }
  }
});
</script>
