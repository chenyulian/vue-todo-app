<template>
<div class="input-add">
    <input type="text" v-model="todoContent" />
    <button @click="EmitAddOne"><i class="plus"></i></button>
</div>
</template>

<script>
import {
    ref,
    computed
} from "vue";
export default {
    props: ["tid"],
    setup(props, context) {
        const todoContent = ref("");
        const EmitAddOne = () => {
            context.emit("addOneTodo", todo);
            todoContent.value = "";
        };
        const todo = computed(() => ({
            id: props.tid,
            content: todoContent.value,
            complete: false,
        }));
        return {
            todoContent,
            EmitAddOne,
            todo,
        };
    },
};
</script>

<style scoped>
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
    outline: none;
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
</style>
