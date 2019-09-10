<template>
<div>
<div v-bind:key="todoItem.id" v-for="todoItem in todoGroupProps">
<TodoItem v-bind:todoItem="todoItem"  v-on:del-todo="$emit('del-todo',todoItem.id)"/>
</div>
</div>
</template>

<script>
import TodoItem from './TodoItem.vue'

export default {
    name: "TodoGroup",
    components: {
        TodoItem
    },
    props: ["todoGroupProps"]
}
</script>
 
<style scoped>

</style>
