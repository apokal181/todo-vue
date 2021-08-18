<template>
  <section>
    <div class="container">
      <Header/>
      <Input :todos="todos"/>
      <h4 v-if="todos.length === 0"> No todos</h4>
      <Todo :todos="todos"/>
    </div>
  </section>
</template>

<script>
import Header from "~/components/Header";
import Todo from "~/components/Todo";
import Input from "~/components/Input";
export default {
  components: {Input, Todo, Header},

  data() {
    return {
      todos: [],
    }
  },

}
</script>

<style>
h4 {
  font-size: 26px;
  text-align: center;
  color: white;
}
body {
  padding: 0;
  margin: 0;
}

section {
  height: 100vh;
  width: 100vw;
  background: #1d1e22;
}
</style>
