<template>
  <draggable class="dragArea" tag="ul" :list="tasks" :group="{ name: 'g2sdsdsdsds' }" item-key="name">
    <template #item="{ element }">


      <div class="card">
        <h3>{{ element.name }}</h3>
        <div class="card border col-md-10 offset-md-1 mt-2">
        <nested-draggable :tasks="element.tasks" />
      </div>

      </div>



    </template>





  </draggable>
</template>
<script>
import draggable from "vuedraggable";

export default {
  props: {
    tasks: {
      required: true,
      type: Array
    }
  },
  components: {
    draggable
  },
  name: "nested-draggable"
};
</script>
<style scoped>
.dragArea {
  min-height: 50px;
  outline: 1px solid black;

}
</style>