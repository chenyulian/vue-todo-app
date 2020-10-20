<template>
<div class="todo-list">
    <template v-for="todo in todos" :key="todo.id">
        <todo-item :todo="todo" @changeState="todo.complete = $event" />
    </template>
</div>
</template>

<script>
import TodoItem from "./TodoItem.vue";
export default {
    props: {
        todos: {
            type: Array,
        },
    },
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
