<template>
  <div id="app">
    <Header />
    <Form @todo-added="addTodo($event)" />
    <TodoList :todo-list="todoList" @delete-todo="deleteTodo($event)" />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Form from './components/Form.vue';
import TodoList from './components/TodoList.vue';
import { ref, reactive, watch } from 'vue';

export default {
  name: 'App',
  components: {
    Header,
    Form,
    TodoList,
  },
  setup() {
    let todoList = reactive([]);

    const addTodo = (event) => {
      todoList.push({
        isDone: false,
        todo: event.value,
        id: Math.random(),
      });
    };

    const deleteTodo = (event) => {
      todoList.splice(event, 1);
    };

    watch(todoList, (newVal) => {
      console.log(newVal, '====>>>>>');
    });

    return {
      addTodo,
      todoList,
      deleteTodo,
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  /* -webkit-font-smoothing: antialiased; */
  /* -moz-osx-font-smoothing: grayscale; */
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
