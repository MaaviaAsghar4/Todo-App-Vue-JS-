<template>
  <div class="listContainer">
    <div class="listItem" v-for="(todos, index) in todoList" :key="index">
      <div>
        <input type="checkbox" v-model="todos.isDone" />
        <span>{{todos.todo}}</span>
      </div>
      <span class="deleteBtn"> &times; <span>
    <div>
  <div>
</template>

<script>
  // import { ref } from "vue"

  export default {
    name: 'TodoList',
    setup () {
      const todoList = [
        {id: 1, todo: 'Todo 1', isDone: false},
        {id: 2, todo: 'Todo 2', isDone: true},
        {id: 3, todo: 'Todo 3', isDone: false},
        {id: 4, todo: 'Todo 4', isDone: false},
      ];

      return {
        todoList
      }
    }
  }
</script>

<style scoped>
  .listContainer {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 15px;
  }
  .listItem {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    max-width: 300px;
    padding: 10px;
    background-color: #efefef;
    margin-top: 10px;
    border-radius: 5px
  }

  .deleteBtn {
    cursor: pointer;
    font-size: 20px;
  }

  .deleteBtn:hover {
    display: block;
    background-color: #2c3e50;
    color: #f2f2f2;
    border-radius: 3px;
  }
</style>
