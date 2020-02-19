<template>

  <q-page padding>
    <button>
      {{counter}}
    </button> 



    <input
    v-model="message"
    @keyup.esc="clearMessage"
    @keyup.enter="alertMessage"
    v-autofocus
    :style="errorStyle"
     />

    <button @click="clearMessage" >Clear</button>
     <div> {{ message.length}} </div>
    <h5 class="bordershow" 
    v-if="message.length"> {{ message }}</h5>

    <h6 v-else>No message displayed!</h6>
    <hr>
     uppercase message : {{ messageUppercase }}
     <br>
     LowercaseMessage : {{message | messagelowercase}}  
  </q-page>
</template>

<script>
  export default {
    data() {
      return {
        message: 'I Love tasks!',
        counter : 0
      }
    },
    computed: {
         messageUppercase(){
      console.log('Message uppercase fired')
     return this.message.toUpperCase()

    },
    errorStyle(){
      if(this.message.length > 22){
        return {
          'background' : 'pink',
          'color' : 'red'
        }
      }

    }
    },
    methods : {
      clearMessage(){
        this.message = ''
      },
    alertMessage(){
        alert(this.message)
    },
 
    },
    filters : {
      messagelowercase(value){
        return value.toLowerCase()
      }
    },
    directives:{
      autofocus : {
        inserted(el){
         el.focus()
        }
      }
    },
    beforeCreate(){
      console.log('before created');
    },
    created(){
       console.log('created');
    },
     beforeMount(){
       console.log('beforeMount');
    },
     mounted(){
       console.log('mounted');
    },
         beforeUpdate(){
       console.log('beforeUpdate');
    },
             updated(){
       console.log('beforeUpdate');
    },
                 beforeDestroy(){
       console.log('beforeDestroy');
    },
                 destroyed(){
       console.log('destroyed');
    },
  }
</script>
<style>
.bordershow {
border: 1px solid grey;
}
.error {
  color:red;
  background: pink;
}
</style>
