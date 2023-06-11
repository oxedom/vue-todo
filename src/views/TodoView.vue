<template lang="">
  <div>
    <Navbar />
    <main v-for="todo in todos" class="grid grid-cols-3 justify-items-center">
      <Todo @completed-toogle="handleToogle" :key="todo.id" v-bind="{ todo }" />
    </main>
  </div>
</template>
<script>
import { ref } from 'vue'
import Navbar from '../components/Navbar.vue'
import Todo from '../components/Todo.vue'

export default {
  components: { Navbar, Todo },
  setup(props) {
    const todos = ref([
      {
        id: 1,
        title: 'Buy groceries',
        text: 'Milk, eggs, bread',
        completed: false
      },
      {
        id: 2,
        title: 'Exercise',
        text: 'Go for a run in the park',
        completed: true
      },
      {
        id: 3,
        title: 'Read book',
        text: "Finish reading 'The Great Gatsby'",
        completed: false
      }
    ])
    function handleToogle(value) {
      let index = todos.value.findIndex((t) => t.id.toString() === value.toString())
      todos.value[index]['completed'] = true
    }



    return { todos, handleToogle }
  }
}
</script>
<style></style>
