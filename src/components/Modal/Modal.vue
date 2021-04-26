<template>
    <teleport to="#moadl">
        <div id="center" v-if="isOpend">
            <h2>
                <slot>this is a modal</slot>
            </h2>
            <button @click="closeModal">close</button>
        </div>
    </teleport>
</template>
<script lang="ts">
import { defineComponent } from 'vue'
export default defineComponent({
    props: {
        isOpend: Boolean,
    },
    emits: {
        'close-modal': null
    },
    setup(props, context) {
        const closeModal = ()  => {
            context.emit('close-modal')
        }
        return {
            closeModal
        }
    }
})
</script>