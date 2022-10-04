<template>
  <div class="listContainer">
    <div  v-for="(todos, index) in todoList" :key="index" :class="{listItemDone : todos.isDone, listItem: !todos.isDone }">
      <div>
        <input class="checkbox" type="checkbox" v-model="todos.isDone" />
        <span>{{todos.todo}}</span>
      </div>
      <span @click="deleteTodos(todos.id)" class="deleteBtn"> &times; <span>
    <div>
  <div>
</template>

<script>
  import { ref, watch } from "vue";

  export default {
    name: 'TodoList',
    props: {
      newTodo: String
    },
    setup (props) {
      console.log(props)
      let todoList = ref([
        {id: 1, todo: 'Todo 1', isDone: false},
        {id: 2, todo: 'Todo 2', isDone: true},
        {id: 3, todo: 'Todo 3', isDone: false},
        {id: 4, todo: 'Todo 4', isDone: false},
      ]);

      const deleteTodos = (id) => {
        let filteredLists = todoList.value.filter(val => val.id !== id);
        todoList.value = filteredLists
      }

      

      return {
        todoList,
        deleteTodos
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
    background-color: #db3236;
    color: #f2f2f2;
    margin-top: 10px;
    border-radius: 5px
  }

  .listItemDone {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    max-width: 300px;
    padding: 10px;
    background-color: #3cba54;
    color: #f2f2f2;
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
