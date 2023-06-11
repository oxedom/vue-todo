<template lang="">
    <div>
      <Navbar/>
      <main v-for="todo in todos" class="grid grid-cols-3  justify-items-center">
            <Todo v-bind={todo} />
            
      </main>
    </div>
  </template>
  <script>
  import { ref } from 'vue';
import Navbar from '../components/Navbar.vue';
import Todo from '../components/Todo.vue';

  export default {
    components: {Navbar, Todo},
    setup(props) {

        const list = [
  {
    title: "Buy groceries",
    text: "Milk, eggs, bread",
    completed: false
  },
  {
    title: "Exercise",
    text: "Go for a run in the park",
    completed: true
  },
  {
    title: "Read book",
    text: "Finish reading 'The Great Gatsby'",
    completed: false
  }
];




        const todos = ref([...list]) 

        return { todos}
    }   

  }
  </script>
  <style>
    
  </style>