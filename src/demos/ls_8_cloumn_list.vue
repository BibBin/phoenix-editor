<template>
  <div class="container">
   <column-list :list="list" />
  </div>
</template>
<script lang="ts">
import { defineComponent } from 'vue';
import ColumnList, { ColumnProps } from '@/components/ColumnList/ColumnList.vue'
const testData:ColumnProps[] = [
    {
        id:1,
        title: 'test1专栏',
        description: 'Vue2 核心成员战斗力：几天内把 Flow 重构为 TypeScript！'
    },
    {
        id:2,
        title: 'test2专栏',
        avatar: 'https://images.dog.ceo/breeds/terrier-irish/n02093991_3604.jpg',
        description: 'Vue2 核心成员战斗力：几天内把 Flow 重构为 TypeScript！'
    },
    {
        id:3,
        title: 'test3专栏',
        avatar: 'https://images.dog.ceo/breeds/terrier-irish/n02093991_3604.jpg',
        description: 'Vue2 核心成员战斗力：几天内把 Flow 重构为 TypeScript！'
    },
    {
        id:4,
        title: 'test4专栏',
        avatar: 'https://images.dog.ceo/breeds/terrier-irish/n02093991_3604.jpg',
        description: 'Vue2 核心成员战斗力：几天内把 Flow 重构为 TypeScript！'
    },
    {
        id:5,
        title: 'test3专栏',
        avatar: 'https://images.dog.ceo/breeds/terrier-irish/n02093991_3604.jpg',
        description: 'Vue2 核心成员战斗力：几天内把 Flow 重构为 TypeScript！'
    },
    {
        id:6,
        title: 'test4专栏',
        avatar: 'https://images.dog.ceo/breeds/terrier-irish/n02093991_3604.jpg',
        description: 'Vue2 核心成员战斗力：几天内把 Flow 重构为 TypeScript！'
    },
    {
        id:7,
        title: 'test3专栏',
        avatar: 'https://images.dog.ceo/breeds/terrier-irish/n02093991_3604.jpg',
        description: 'Vue2 核心成员战斗力：几天内把 Flow 重构为 TypeScript！'
    },
    {
        id:8,
        title: 'test4专栏',
        avatar: 'https://images.dog.ceo/breeds/terrier-irish/n02093991_3604.jpg',
        description: 'Vue2 核心成员战斗力：几天内把 Flow 重构为 TypeScript！'
    }
]
export default defineComponent({
  name: 'Home',
  components: {
    ColumnList,
  },
  setup() {
      return {
      list: testData
      }
  }
});
</script>
