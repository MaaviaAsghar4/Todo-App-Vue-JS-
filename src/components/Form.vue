<template>
  <form>
    <label>Enter Todo</label>
    <input id="type-text" type="text" placeholder="Add Task" />
    <input id="type-submit" type="submit" />
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
  max-width: 300px;
  width: 100%;
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
