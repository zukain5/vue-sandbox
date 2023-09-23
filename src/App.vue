<script setup lang="ts">
export interface Item {
  name: string;
}
</script>

<script lang="ts">
export default {
  data() {
    return {
      items: [] as Item[],
    }
  },
  computed: {
    num(){
      return this.items.length
    },
  },
  methods: {
    add(){
      const userName = 'Item' + (this.num + 1);
      this.items.push({ name: userName });
    },
    reset(){
      this.items = [];
    },
  }
}
</script>

<template>
  <p>Number of items: {{ num }}</p>
  <button @click="add">Add an item</button>
  <button @click="reset">Reset</button>
  <ul>
    <li v-for="item in items" :key="item.name">{{ item.name }}</li>
  </ul>
</template>
