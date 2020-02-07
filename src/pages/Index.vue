<template>
  <q-page padding>
    <input
    v-model="message"
    @keyup.esc="clearMessage"
    @keyup.enter="alertMessage" />

    <button @click="clearMessage" >Clear</button>

    <h5 class="bordershow" 
    v-if="message.length"> {{ message }}</h5>

    <h6 v-else>No message displayed!</h6>
    <hr>
     uppercase message : {{ uppercasMessage() }}

  </q-page>
</template>

<script>
  export default {
    data() {
      return {
        message: 'I Love tasks!'
      }
    },
    methods : {
      clearMessage(){
        this.message = ''
      },
    alertMessage(){
        alert(this.message)
    },
    uppercasMessage(){
      this.message.uppercaseMessage()
    }
    }
  }
</script>
<style>
.bordershow {
border: 1px solid grey;
}
</style>
