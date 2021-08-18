<template>
  <div class="container">
    <div class="form-container">
      <form @submit.prevent="submitHandler" class="input-form">
        <input v-model="text" type="text" @keypress="inputHandler" class="add-input">
        <button type="submit" class="add-button">ADD</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      text: '',
    }
  },
  methods: {
    saveData() {
      const storageData = JSON.stringify(this.todos);
      localStorage.setItem('todos', storageData);
    },

    inputHandler(e) {
      this.text = e.target.value
    },
    submitHandler() {
      this.todos.push({
        text: this.text,
        done: false
      })
      this.text = ''
      this.saveData()
    },
  },
  props: ['todos']
}
</script>

<style>

.form-container {
  display: flex;
  margin-bottom: 40px;
  margin-top: 40px;
}

.add-button {
  font-weight: bold;
  font-size: 22px;
  margin-left: 10px;
  border-radius: 4px;
  cursor: pointer;
  color: white;
  width: 10%;
  height: 50px;
  border: 2px solid darkgoldenrod;
  background: transparent;
}

.add-button:hover {

  background: crimson;
  transition: 500ms;
}
.input-form {
  width: 800px;
  display: flex;
  margin: 0 auto;
}

.add-input {
  border-radius: 4px;
  background: #1d1e22;
  font-size: 24px;
  color: white;
  border: 2px solid darkgoldenrod;
  width: 70%;
  height: 44px;
}
</style>
