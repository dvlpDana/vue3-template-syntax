<template>
  <!-- Remove & use example component! -->
  <h1
    :[attr]="status"
    @[event]="add">
    {{ difMessage }}
  </h1>
  
  <HelloWorld 
    :msg="message" 
    @click="handler" />
  <HelloWorld msg="Good" />
</template>

<script>
import HelloWorld from '~/components/HelloWorld'

export default {
  components: {
    HelloWorld
  },
  data() {
    return {
      message: 'Hello Vue!',
      difMessage: "Goodbye Vue!",
      status: 'active',
      attr: 'class',
      event: 'click'
    }
  },
  methods: {
    handler() {
      console.log(this.message)
      this.message += '!'
    },
    add() {
      console.log(this.difMessage)
      this.difMessage += '!'
    }
  }
}
</script>

<style scoped>
  .active{
    font-size: 40px;
    color : royalblue;
  }
</style>
