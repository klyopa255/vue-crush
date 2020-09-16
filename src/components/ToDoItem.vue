<template>
    <li>
        <span :class="{done: todo.completed}">
            <input
                type="checkbox"
                @change="todo.completed = !todo.completed"
            >
            <strong>{{ todo.id }}</strong>
            {{ todo.title }}
        </span>
        <button
            class="rm"
            @click="$emit('remove-todo', todo.id)"
        >&times;</button>
    </li>
</template>

<script>
export default {
    props: {
        todo: {
            type: Object,
            requared: true
        }
    }
}
</script>

<style scoped>
li {
    border: 1px solid #ccc;
    display: flex;
    justify-content: space-between;
    padding: 0.5rem 2rem;
    margin-bottom: 1rem;
}
.rm {
    background-color: red;
    color: #fff;
    border-radius: 50%;
    font-weight: bold;
    cursor: pointer;
}
.done {
    text-decoration: line-through;
}
input {
    margin-right: 1rem;
    cursor: pointer;
}
</style>