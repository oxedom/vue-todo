<template lang="">
    <form class="border-black border-2 p-2 flex justify-center items-center bg-gray-200 flex-col gap-2" @submit.prevent="handleSumbit">
        <input type="text" :v-bind=newTitle onUpdated=handleInput />
        <button > Add todo </button>
    </form>
</template>
<script>
import {ref} from 'vue'

export default {
setup() 
{
    const newTitle = ref("")
    function handleInput(e) {
        newTitle - e.target.value
    }
    function handleSubmit(e) {
        e.preventDefault()
    }


    return { handleInput, handleSubmit, newTitle}

}

}
</script>
<style lang="">
    
</style>