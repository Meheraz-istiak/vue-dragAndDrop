<template>
  <div class="containar">
    <div class="row">
    <div class="col-md-8">
      <h3>Nested draggable</h3>
      <nested-draggable :tasks="list" />
    </div>

    <!-- <rawDisplayer class="col-3" :value="list" title="List" /> -->
  </div>
  </div>


</template>

<script>
import nestedDraggable from './components/infra/nested.vue';
export default {
  name: "nested-example",
  display: "Nested",
  order: 15,
  components: {
    nestedDraggable
  },
  data() {
    return {
      list: [
        {
          name: "task 1",
          tasks: [
            {
              name: "task 2",
              tasks: []
            }
          ]
        },
        {
          name: "task 3",
          tasks: [
            {
              name: "task 4",
              tasks: []
            }
          ]
        },
        {
          name: "task 5",
          tasks: []
        }
      ]
    };
  }
};
</script>
<style scoped>
 .border{
  border: 1px solid black;
 }
</style>