<template>
    <div>
        <p v-bind:class= "{ completed: todo.completed}">
            <input type="checkbox" v-on:change = "onCompleteChangeHandler">
            {{todo.text}}
            <button v-on:click="onDeleteHandler(todo.id)">delete</button>
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
            },
            onDeleteHandler(id) {
                this.$emit("deleteTodo", id)
            }
        }
    }
</script>
<style scoped>
    .completed {
        text-decoration: line-through;
    }
</style>