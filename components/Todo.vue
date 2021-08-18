<template>
  <section>
    <div class="container">
      <SingleTodo :todos="todos"/>

    </div>
  </section>
</template>

<script>
import SingleTodo from "~/components/SingleTodo";
export default {
  components: {SingleTodo},
  data() {
    return {

    }
  },
  props: ['todos']
}
</script>

<style>

  .todos div {
    margin-bottom: 10px;
    font-weight: bold;
    font-size: 18px;
    padding: 20px;
    color: white;
    border: 1px solid darkgoldenrod;
  }
  .todos {
    margin: 0 auto;
    width: 1000px;
  }
</style>
