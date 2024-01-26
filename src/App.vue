<template>
  <div>
    <todo-hedaer />
    <todo-input />
    <todo-list />
    <todo-footer />
  </div>
</template>

<script>
import TodoHedaer from './components/TodoHedaer.vue'
import TodoInput from './components/TodoInput.vue'
import TodoList from './components/TodoList.vue'
import TodoFooter from './components/TodoFooter.vue'

export default {
  components: {
    TodoHedaer,
    TodoInput,
    TodoList,
    TodoFooter
  }
}
</script>

<style>
body {
  font-family: 'Ubuntu';
  background-color: #F6F6F6;
}
input {
  border-style: groove;
  width: 200px;
}
button {
  border-style: groove;
}
.shadow {
  box-shadow: 5px 10px 10px rgba(0, 0, 0, 0.03);
}
</style>
