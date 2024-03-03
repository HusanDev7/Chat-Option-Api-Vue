<template>
  <main class="app__chat-main"> 
     <TransitionGroup name="list">
      <div class="app__chat-main-item" v-for="(mess, index) in massage" :key="index">
  <div class="app__chat-main-body" :class="{
    send: mess.sendId == sendId,
    get: mess.sendId != sendId,
  }">
    <span class="app__chat-main-time">{{ mess.time }}</span>
    <div class="app__chat-main-text">
      <p>{{ mess.body }}</p>
    </div>
  </div>
</div>
     </TransitionGroup>
  </main>
</template>

<script>
export default {
    props: {
      massage: Array,
      sendId: Number,
    }
}
</script>

<style>

</style>



