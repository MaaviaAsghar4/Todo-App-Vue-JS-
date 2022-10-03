<template>
  <form>
    <label>Enter Todo</label>
    <input type="text" placeholder="Add Task" />
    <input type="submit" />
  </form>
</template>

<script>
export default {
  name: 'Form',
};
</script>

<style>
form {
  display: flex;
  flex-direction: column;
  width: fit-content;
}

label {
  align-self: flex-start;
  font-size: 12px;
  color: #000;
  font-weight: 600;
  margin-bottom: 5px;
}

input {
  margin-bottom: 10px;
  width: 100%;
  max-width: 300px;
}
</style>
