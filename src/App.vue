<template>
  <div id="app">
    <Header />
    <Form @todo-added="addTodo($event)" />
    <TodoList :new-todo="newTodo" />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Form from './components/Form.vue';
import TodoList from './components/TodoList.vue';
import { ref, watch } from 'vue';

export default {
  name: 'App',
  components: {
    Header,
    Form,
    TodoList,
  },
  setup() {
    let newTodo = ref('');

    const addTodo = (event) => {
      newTodo.value = event.value;
    };

    // watch(newTodo, (newVal) => {
    //   console.log(newVal, '====>>>>');
    //   newTodo.value = newVal;
    // });

    return {
      addTodo,
      newTodo,
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
