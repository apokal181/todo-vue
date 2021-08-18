<template>
    <ul>
      <li
        class="single-todo"
        :class="{active: todo.done}"
        v-for="(todo, index) in todos"
        :key="index"
        @click="todoDone(todo)"
      >
        {{index+1}}. {{(todo.text).toUpperCase()}}
        <button @click="removeTodo(index)" class="delete-btn">delete</button>

      </li>



    </ul>
</template>

<script>
  export default {
    data() {
      return {
        isActive: false,
      }
    },
    methods: {
      saveData() {
        if(process.browser) {
          const storageData = JSON.stringify(this.todos);
          localStorage.setItem('todos', storageData);
        }
      },
      removeTodo (index) {
        this.todos.splice(index, 1);
         this.saveData();
      },

      todoDone(todo) {
        todo.done = !todo.done
        this.isActive = !this.isActive
        this.saveData();
      },
    },
    props: ['todos'],
  }
</script>

<style>
.span-btn {
  float: right;
}
.delete-btn {
  width: 85px;
  height: 42px;
  color: white;
  background: firebrick;
  border: none;
  float: right;
  border-radius: 8px;
}
.delete-btn:hover {
  background: darkgoldenrod;
  transition: 500ms;
  cursor: pointer;
}
.single-todo {
  border-radius: 20px;
  font-size: 36px;
  list-style-type: none;
  cursor: pointer;
  margin: 0 auto;
  width: 1000px;
  margin-bottom: 10px;
  border: 1px solid darkgoldenrod;
  font-weight: bold;
  padding: 20px;
  color: white;
}
.active {
  border: 1px solid greenyellow;
  text-decoration: line-through;
}
</style>
