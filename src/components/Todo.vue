<template lang="">
    <section @click=handleClick :class="[completed ? 'bg-green-500' : 'bg-red-500',]">
        <h3 class="text-2xl text-center" >         {{title}} </h3>
        <p>         {{text}}
 </p>
    </section>
</template>
<script>
export default {
    props: ['todo'],
    setup(props) 
    {
    function handleClick(e) 
    {
        
    }

    const { title, completed, text} = props.todo
    
    return { title, completed, text, handleClick}
    }
}
</script>
<style lang="">
    
</style>