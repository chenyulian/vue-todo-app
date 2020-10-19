<template>
<main>
    <div class="container">
        <h1>待办事项</h1>
        <div class="input-add">
            <input type="text" />
            <button><i class="plus"></i></button>
        </div>

        <div class="filters">
            <span class="filter active">全部</span>
            <span class="filter">已完成</span>
            <span class="filter">未完成</span>
        </div>
        <div class="todo-list">
            <div class="todo-item">
                <label><input type="checkbox" />TO DO 1<span class="check-button"></span></label>
            </div>
            <div class="todo-item">
                <label><input type="checkbox" /> TO DO 2<span class="check-button"></span></label>
            </div>
            <div class="todo-item">
                <label><input type="checkbox" /> TO DO 3<span class="check-button"></span></label>
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

<style scoped>
main {
    height: 100vh;
    width: 100vw;
    display: flex;
    align-content: center;
    justify-content: center;
    background-color: rgb(203, 210, 240);
}

.container {
    width: 60%;
    max-width: 400px;
    display: block;
    box-shadow: 0px 0px 24px rgba(0, 0, 0, 0.15);
    border-radius: 24px;
    padding: 24px 18px;
    background-color: rgb(245, 246, 252);
    padding: 48px 28px;
    margin: 100px 0;
    overflow: auto;
}

h1 {
    margin: 24px 0;
    font-size: 28px;
    color: #414873;
}

.input-add {
    position: relative;
    display: flex;
    align-items: center;
}

.input-add input {
    padding: 16px 52px 16px 18px;
    border-radius: 48px;
    border: none;
    outline: none;
    box-shadow: 0px 0px 24px rgba(0, 0, 0, 0.08);
    width: 100%;
    font-size: 16px;
    color: #626262;
}

.input-add button {
    width: 46px;
    height: 46px;
    border-radius: 50%;
    background: linear-gradient(#c0a5f3, #7f95f7);
    border: none;
    color: white;
    position: absolute;
    right: 0px;
}

.input-add .plus {
    display: block;
    width: 100%;
    height: 100%;
    background: linear-gradient(#fff, #fff), linear-gradient(#fff, #fff);
    background-size: 50% 2px, 2px 50%;
    background-position: center;
    background-repeat: no-repeat;
}

.filters {
    display: flex;
    margin: 24px 2px;
    color: #c0c2ce;
    font-size: 14px;
}

.filters .filter {
    margin-right: 14px;
    transition: 0.8s;
}

.filters .filter.active {
    color: #6b729c;
    transform: scale(1.2);
}

.todo-list {
    display: grid;
    row-gap: 14px;
}

.todo-item {
    background: white;
    padding: 16px;
    border-radius: 8px;
    color: #626262;
}

.todo-item label {
    position: relative;
    display: flex;
    align-items: center;
}

.todo-item label span.check-button {
    position: absolute;
    top: 0;
}

.todo-item label span.check-button::before,
.todo-item label span.check-button::after {
    content: "";
    display: block;
    position: absolute;
    width: 18px;
    height: 18px;
    border-radius: 50%;
}

.todo-item label span.check-button::before {
    border: 1px solid #b382f9;
}

.todo-item label span.check-button::after {
    transition: 0.4s;
    background: #b382f9;
    transform: translate(1px, 1px) scale(0.8);
    opacity: 0;
}

.todo-item input {
    margin-right: 16px;
    opacity: 0;
}

.todo-item input:checked+span.check-button::after {
    opacity: 1;
}
</style>
