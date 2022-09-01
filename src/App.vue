<script setup>
  import Header from './components/Header.vue'
  import {ref} from 'vue'
  import TodoList from './components/TodoList.vue'

  const todos = ref([])
  const newTodo = ref("")

  const addTodo = () => {
    todos.value.push(newTodo.value)
    newTodo.value=""
  }

  const removeTodo = (index) => {
    todos.value.splice(index, 1)
  }
</script>

<template>
  <Header color='red'>My Todo</Header>
  <!-- //双方向バインディングはv-model -->
  <input type="test" size="30" v-model="newTodo">
  <!-- @click->v-on:clickの略 -->
  <button @click="addTodo">追加</button>
  <TodoList :todos='todos' @removeTodo='removeTodo'/>
</template>