<template>
  <draggable v-bind="items" :options="dragOptions">
    <div v-for="(item, index) in items" :key="index" class="accordion-item">
      <div class="accordion-header" @click="toggleItem(item)">
        {{ item.title }}
      </div>
      <div class="accordion-content" v-show="item.open">
        {{ item.content }}
        <nested-accordion :items="item.children"></nested-accordion>
      </div>
    </div>
  </draggable>
</template>

<script>
import draggable from 'vuedraggable';

export default {
  components: {
    draggable,
  },


  data() {
    return {
      items: [
  {
    header: 'Item 1 Header',
    content: 'Item 1 Content',
    open: false,
    children: [
      // Nested items go here with the same structure
    ],
  },
  {
    header: 'Item 2 Header',
    content: 'Item 2 Content',
    open: false,
    children: [
      // Nested items go here with the same structure
    ],
  },
  // ... more items
],
      dragOptions: {
        group: 'accordion',
      },
    };
  },
  methods: {
    toggleItem(item) {
      item.open = !item.open;
    },
  },
};
</script>

<style>
.accordion-item {
  border: 1px solid #ccc;
  margin: 10px;
  padding: 10px;
  background-color: #f9f9f9;
}

.accordion-header {
  cursor: pointer;
}

.accordion-content {
  display: none;
}
</style>
