<template>
<main>
    <div class="container">
        <input type="text" />
        <div class="filters">
            <span>全部</span>
            <span>已完成</span>
            <span>未完成</span>
        </div>
        <div class="todo-list">
            <div class="todo-item">
                <input type="checkbox" /> <label>TO DO 1</label>
            </div>
            <div class="todo-item">
                <input type="checkbox" /> <label>TO DO 2</label>
            </div>
            <div class="todo-item">
                <input type="checkbox" /> <label>TO DO 3</label>
            </div>
        </div>
    </div>
</main>
</template>

<script>
export default {
    name: "App",
    components: {},
};
</script>
