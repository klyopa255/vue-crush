<template>
    <div>
        <ul>
            <ToDoItem
                v-for="todo of todos"
                v-bind:todo="todo"
                :key="todo.id"
                @remove-todo="removeToDo"
            />
        </ul>
    </div>
</template>

<script>
import ToDoItem from '@/components/ToDoItem'
export default {
    props: ['todos'],
    components: {
        ToDoItem
    },
    methods: {
        removeToDo(id) {
            this.$emit('remove-todo', id)
        }
    }
}
</script>

<style scoped>
ul {
    margin: 0;
    padding: 0;
    list-style: none;
}
</style>