<template>
    <div>
        <h1> Todos </h1>
        <div>
            <TodoItem  v-on:deleteTodo= "deleteTodo($event)" v-bind:key="todo.id" v-for="todo in todos" v-bind:todo = "todo" />
        </div>
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

</style>