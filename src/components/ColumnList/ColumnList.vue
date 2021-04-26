<template>
<div class="row">
    <div class="col-3 mb-3" v-for="column in columnList" :key="column.id">
       <div class="card h-100 shadow-sm">
           <div class="card-body text-center">
            <img class="rounded-circle border border-light w-25 my-3" :src="column.avatar" :alt="column.title" >
            <h5 class="card-title">{{ column.title }}</h5>
            <p class="card-text text-left">{{ column.description }}</p>
            <a href="#" class="btn btn-outline-primary">进入专栏</a>
            </div>
       </div>
    </div>
</div>
</template>
<script lang="ts">
import { computed, defineComponent, PropType } from 'vue'
export interface ColumnProps {
    id: number;
    title: string;
    avatar?: string;
    description: string;
}
export default defineComponent({
    name: 'ColumnList',
    props: {
        list: {
            // 构造函数断言成类型，需使用PropType
            type: Array as PropType<ColumnProps[]>,
            require: true
        }
    },
    setup(props){
        const columnList = computed(()=>{
            return props.list&&props.list.map(column => {
                if(!column.avatar) {
                    column.avatar = require('@/assets/logo.png')
                }
                return column
            })
        })
        return {
            columnList
        }
    }
})
</script>