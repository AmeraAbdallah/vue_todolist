<template>
    <div>
        <h1> Todos </h1>
        <div>
            <TodoItem v-bind:key="todo.id" v-for="todo in todos" v-bind:todo = "todo" />
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
        props: ['todos']
    }
</script>

<style scoped>

</style>