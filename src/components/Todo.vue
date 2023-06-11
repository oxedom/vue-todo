<template lang="">
  <section @click="handleClick" :class="[completed.value ? 'bg-green-500' : 'bg-red-500']">
    <h3 class="text-2xl text-center">{{ title }}</h3>
    <p>{{ text }}</p>
  </section>
</template>
<script>
import { ref, getCurrentInstance, onUpdated } from 'vue'

export default {
  props: ['todo'],
  setup(props) {
    const { id, title, text } = props.todo
    const instance = getCurrentInstance()
    const completed = ref(props.todo.completed)
    function handleClick(e) {
      instance.emit('completed-toogle', props.todo)
    }



    return { id, title, completed, text, handleClick }
  }
}
</script>
<style lang=""></style>
