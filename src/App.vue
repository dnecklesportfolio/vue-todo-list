<template>
  <div id="app">
    <TodoHeader/>
  <TodosGroup v-bind:todoGroupProps="todoData" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import TodoHeader from './components/layouts/TodoHeader'
import TodosGroup from './components/TodoGroup'

export default {
  name: 'app',
  components: {
  TodoHeader,
  TodosGroup
  
  },
  data() {
    return { 
      todoData:[
        {
          id: 1,
          title:"Todo One",
          completed: false

        },
        {
          id: 2,
          title:"Todo Two",
         completed: true
        },
        {
          id: 3,
          title:"Todo Three",
         completed: false
        },
      ]
       }
  },
  methods: {
    deleteTodo(id) {
      this.todoData = this.todoData.filter(todo => todo.id != id)
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>
