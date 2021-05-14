<template>
  <h1>{{ title }}</h1>
  <div v-if="showModal">
    <Modal theme="" @close="toogleModal">
      <template v-slot:links>
        <a href="#">Get your package now</a>
        <a href="#">More info</a>  
      </template>
      <h1>Choose your module!</h1>
      <p>Each module is explained carefully by our best!</p>
      
    </Modal>
  </div>
  <br>
  <input type="text" ref="name">
  <button @click="handleClick">Click me</button>
  <br>
  <p>Welcome...</p>
  <button @click="toogleModal">Open Modal</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return{
      title: 'My First Vue App :)',
      header: 'Sign up for learning more!',
      text: 'Decide on something to learn and get started!',
      showModal: false
    }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    },
    toogleModal() {
      this.showModal = !this.showModal
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px ;
}
</style>
