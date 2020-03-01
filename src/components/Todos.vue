<template>
    <div class="todos-container">
        <TodoItem  v-on:deleteTodo= "deleteTodo($event)" v-bind:key="todo.id" v-for="todo in todos" v-bind:todo = "todo" />
    </div>
</template>

<script>
    import TodoItem from './TodoItem';

    export default {
        name: 'Todos',
        components: {
            TodoItem
        },
        props: ['todos'],
          methods: {
            deleteTodo(id) {
                this.$emit('deleteTodo', id);// this.todos = this.todos.filter((todo) => id !== todo.id)
            }
        }
    }
</script>

<style scoped>
    .todos-container {
        background-color: #545E75;
        color: #F7F7FF;
        width: 70%;
        margin: 0 auto;
    }
</style>