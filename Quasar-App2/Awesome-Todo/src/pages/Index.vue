<template>
  <q-page padding>
    <button
      style="position:absolute; right:10px"
      @click="counter++"
    >
    {{ counter }}
    </button>

    <input
    v-model="message"
    @keyup.esc="clearMessage"
    @keyup.enter="clearMessage"
    v-autofocus 
    :style="errorStyle"/>

    <button @click="clearMessage">Clear</button>

    <div> {{ message.length }}</div>

    <h5 
      v-if="message.length"
      class="border-grey">{{ message }}</h5>
    <h6 v-else>No message entered 😩</h6>

    <hr>

    <p>Uppercase message: {{ messageUppercase }}</p>
    <p>Lowercase message: {{ message | messageLowercase }} </p>
  </q-page>
</template>

<script>
  export default{
    data() {
      return {
        message: 'I love Vue.js so hard!',
        counter: 0
      }
    },
    computed: {
      messageUppercase() {
        console.log('messageUppercase was fired')
        return this.message.toUpperCase() + this.counter
      },
      errorStyle(){
        if (this.message.length > 22) {
          return {
            'color' : 'red',
            'backgroud' : 'pink'
          }
        }
      }
    },
    methods: {
      clearMessage() {
        this.message = ''
      },
      alertMessage() {
        alert(this.message)
      }
    },
    filters: {
      messageLowercase(value) {
        return value.toLowerCase()
      }
    },
    directives: {
      autofocus: {
        inserted(el) {
          el.focus()
        }
      }
    }
  }
</script>

<style>
  .border-grey{
    border: 1px solid grey;
  }

  .error {
    color: red;
    background: pink;
  }
</style>
