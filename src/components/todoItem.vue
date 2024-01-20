<template>
    <div class="todo-item">
       <h3>{{ item.todo }}</h3>
    </div>
</template>

<script setup>
defineProps(['item'])

</script>

<style  scoped>
.todo-item{
    padding: 10px 20px;
    border: 1px solid #ddd;
}
.todo-item:hover{
    cursor:move;
}

</style>