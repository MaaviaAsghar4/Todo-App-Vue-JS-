<template>
  <div id="app">
    <Header />
    <Form />
    <TodoList />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Form from './components/Form.vue';
import TodoList from './components/TodoList.vue';

export default {
  name: 'App',
  components: {
    Header,
    Form,
    TodoList,
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
