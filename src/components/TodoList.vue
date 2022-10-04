<template>
  <div class="listContainer">
    <p v-if="!newList.length">No more todos now...</p>
    <div  v-for="(todos, index) in newList" :key="index" :class="{listItemDone : todos.isDone, listItem: !todos.isDone }">
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
      todoList: Array
    },
    setup (props) {

      let newList = ref(props.todoList)

      const deleteTodos = (id) => {
        let filteredLists = newList.value.filter(val => val.id !== id);
        newList.value = filteredLists
      }

      

      return {
        newList,
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
