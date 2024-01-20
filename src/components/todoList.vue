<template>
    <div class="todo-list">
        <div class="title">
            {{ title }}

        </div>
    <slot></slot>
    </div>
</template>

<script setup>
defineProps(['title'])

</script>

<style  scoped>
.todo-list{
    padding: 10px 20px;
    margin: 0 10px;
    border: 1px solid #eee;
    font-family: sans-serif;
    width: 300px;
}
.title{
    padding: 10px 20px;
    font-size: 20px;
    font-weight: 600;
    margin-bottom: 10px;
    text-align: center;
    border-bottom: 1px solid #eee;
}
</style>