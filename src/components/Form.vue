<template>
  <form @submit.prevent="addTodo()">
    <label>Enter Todo</label>
    <input
      v-model="newTodo"
      id="type-text"
      type="text"
      placeholder="Add Task"
    />
    <input id="type-submit" type="submit" />
  </form>
</template>

<script>
import { ref } from 'vue';

export default {
  name: 'Form',
  emits: ['todoAdded'],
  setup(props, { emit }) {
    let newTodo = ref('');

    const addTodo = () => {
      emit('todoAdded', newTodo);
      newTodo.value = '';
    };

    return {
      newTodo,
      addTodo,
    };
  },
};
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
  align-items: center;
}

label {
  font-size: 12px;
  color: #000;
  font-weight: 600;
  margin-bottom: 5px;
}

#type-submit {
  border: none;
  padding: 10px;
  background-color: #2c3e50;
  color: #f2f2f2;
  cursor: pointer;
  margin-bottom: 10px;
  border-radius: 5px;
}

#type-text {
  border: 1px solid #2c3e50;
  padding: 10px;
  color: #2c3e50;
  margin-bottom: 10px;
  max-width: 300px;
  width: 100%;
  border-radius: 5px;
}
</style>
