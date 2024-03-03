<template>
   <div class="app__chat-header">
      <img :src="people[src]" class="app__chat-header-img" alt="">
       <div class="app__chat-header-info">
      <h1 class="app__chat-header-title">{{ name }}</h1>
      <p class="app__chat-header-status">{{ status }}</p>
    </div>
   </div>
</template>

<script>
export default {
    props: ['src', 'name', 'status'],
    data() {
        return {
            people: {
                john: require( "@src/assets/images/alex.png"),
                alex: require( "@src/assets/images/john.png"),
            } 
        }
    }

    
}
</script>

<style>

</style>