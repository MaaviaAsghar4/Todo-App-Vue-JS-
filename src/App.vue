<template>
  <div id="app">
    <Header />
    <Form @todo-added="addTodo($event)" />
    <TodoList :todo-list="todoList" />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Form from './components/Form.vue';
import TodoList from './components/TodoList.vue';
import { ref } from 'vue';

export default {
  name: 'App',
  components: {
    Header,
    Form,
    TodoList,
  },
  setup() {
    let newTodo = ref('');
    let todoList = ref([]);

    const addTodo = (event) => {
      todoList.value.push({
        isDone: false,
        todo: event.value,
        id: Math.random(),
      });
    };

    return {
      addTodo,
      newTodo,
      todoList,
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
