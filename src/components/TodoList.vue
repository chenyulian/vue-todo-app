<template>
<div class="todo-list">
    <todo-item />
    <todo-item />
</div>
</template>

<script>
import TodoItem from "./TodoItem.vue";
export default {
    components: {
        TodoItem,
    },
};
</script>

<style scoped>
.todo-list {
    display: grid;
    row-gap: 14px;
}
</style>
