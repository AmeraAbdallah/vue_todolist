<template>
    <form @submit="onSubmitHandler">
        <input type="text" v-model="text">
        <input type="submit" value="add" />
    </form>
</template>
<script>
    import {v4} from 'uuid';
    export default {
        data() {
            return {
                text: ''
            }
        },
        methods: {
            onSubmitHandler(e) {
                e.preventDefault();
                let newTodo= {
                    id: v4(),
                    text: this.text,
                    completed: false
                }
                this.$emit('add-todo', newTodo);
                this.text = '';
            }
        }
    }
</script>
<style scoped>

</style>