<template>
    <div>
        <p v-bind:class= "{ completed: todo.completed}">
            <input type="checkbox" v-on:change = "onCompleteChangeHandler">
            {{todo.text}}
        </p>
    </div>
</template>
<script>
    export default {
        name: "TodoItem",
        props: ['todo'],
        methods: {
            onCompleteChangeHandler() {
                this.todo.completed = !this.todo.completed
            }
        }
    }
</script>
<style scoped>
    .completed {
        text-decoration: line-through;
    }
</style>