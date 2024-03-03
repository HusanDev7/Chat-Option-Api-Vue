<template>
  <footer class="app__chat-footer">
    <input @keydown.enter="sendMess" rows="1" placeholder="Написать сообщение..." type="text" class="app__chat-footer-inp"
      v-model="massage">
    <button class="app__chat-footer-btn" v-if="massage.length == 0">
      <img src="../assets/images/img4.svg" alt="">
    </button>

    <button class="app__chat-footer-btn" @click="sendMess" v-else>
      <img src="../assets/images/img1.svg" alt="">
    </button>
  </footer>
</template>

<script>
export default {
  props: {
    sendId: Number
  },

  data() {
    return {
      massage: "",
    }
  },

  methods: {
    sendMess() {
      const time = `${new Date().getHours()}: ${new Date().getMinutes()} `
      if (this.massage.length > 0) {
        const mess = {};
        mess.body = this.massage.trim()
        mess.sendId = this.sendId
        mess.time = time
        this.$emit('new-mess', mess)
        this.massage = ''
      }
    }
  }







}
</script>

<style></style>