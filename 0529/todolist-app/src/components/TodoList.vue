<template>
    <div clasee="row">
        <div class="col">
            <ul class="list-group">
                <TodoListItem v-for="todoItem in todoList" :key="todoItem.id"
                   :todoItem="todoItem" />
            </ul>
        </div>
    </div>
</template>

<script>
    import TodoListItem from './TodolistItem.vue'
    export default {
        name: "TodoList",
        components: {TodoListItem},
        props: {
            todoList: {type: Array, required: true }
        },
    }
</script>

<style scoped>

</style>