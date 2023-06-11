<template lang="">
  <div>
    <Navbar />

    <AddTodo/>
    <main v-for="todo in todos" class="grid grid-cols-3 justify-items-center">
        
      <Todo @completed-toogle="handleToogle" :key="todo.id" v-bind="{ todo }" />
    </main>
  </div>
</template>
<script>
import { ref } from 'vue'
import Navbar from '../components/Navbar.vue'
import Todo from '../components/Todo.vue'
import AddTodo from '../components/AddTodo.vue'
export default {
  components: { Navbar, Todo, AddTodo },
  setup() {
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
    function handleToogle(todo) {
        todo.completed = !todo.completed
        console.log(todo);
    }



    return { todos, handleToogle }
  }
}
</script>
<style></style>
