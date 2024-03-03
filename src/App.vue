<template>
   <Modalchat v-show="modalOpen"/>
   <div class="app">
       <div class="app__chat">
         <Header :src="'alex'" :name="'Александр'" :status="'В сети'"/>
         <Main :sendId="2" :massage="massage"/>
         <Footer :sendId="2" @newMess="newMess"/>
       </div>

       <div class="app__chat">
         <Header :src="'john'" :name="'Евгений'" :status="'В сети'"/>
         <Main :sendId="1" :massage="massage"/>
         <Footer :sendId="1" @newMess="newMess"/>
         
       </div>
   </div>
</template>

<script>

import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import Footer from "./components/Footer.vue";
import Modalchat from "./components/Modalchat.vue";

export default {
    
  components: {
    Header,
    Main,
    Footer,
    Modalchat,
  },
  data(){
    return {
    modalOpen: false,  
    massage: [],
   
    }
  },
  created() {
    const messStorage = localStorage.massage ? JSON.parse(localStorage.massage) : [];
    this.massage = messStorage
  },

  methods: {
    newMess(mess) {
      this.massage.push(mess)
      localStorage.massage = JSON.stringify(this.massage)
    }
  }




};
</script>

<style>
  

</style>