<template>
  <div>
    <nestable
    v-bind ="items"
      :options="nestableOptions"
      class="nestable"
    >
      <template #item="{ item }">
        <div class="nestable-item">
          <div class="nestable-header" @click="toggleItem(item)">
            {{ item.title }}
          </div>
          <div class="nestable-content" v-if="item.open">
            {{ item.content }}
          </div>
        </div>
      </template>
    </nestable>
  </div>
</template>

<script>
import VueNestable from 'vue-nestable';

export default {
  components: {
    nestable: VueNestable,
  },
  props: {
    items: Array,
  },
  data() {
    return {
      nestableOptions: {
        maxDepth: 5, // Set your desired max nesting depth
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

<style scoped>
.nestable-item {
  margin: 10px;
  padding: 10px;
  background-color: #f9f9f9;
  border: 1px solid #ccc;
}

.nestable-header {
  cursor: pointer;
}

.nestable-content {
  display: none;
}
</style>
