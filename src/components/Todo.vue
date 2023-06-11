<template lang="">
  <section @click="handleClick" :class="[completed ? 'bg-green-500' : 'bg-red-500']">
    <h3 class="text-2xl text-center">{{ title }}</h3>
    <p>{{ text }}</p>
  </section>
</template>
<script>
import { getCurrentInstance } from 'vue'
export default {
  props: ['todo'],
  setup(props) {
    const instance = getCurrentInstance()
    const { id, title, completed, text } = props.todo
    function handleClick(e) {
      instance.emit('completed-toogle', id)
    }

    return { id, title, completed, text, handleClick }
  }
}
</script>
<style lang=""></style>
