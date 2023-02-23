<template>
  <h1>{{title}}</h1>
  <div v-if="showModal">
    <Modal :header="header" :text="text" theme="sale" @click="toggleModal"/>
  </div>
  <br><br><br><br>
  <button @click="toggleModal">ShowModal</button>

</template>

<script>
import Modal from "../src/components/Modal.vue"
export default {
  name: 'App',
  components:{
    Modal
  },
  data() {
    return {
      title: 'My First VueJS app',
      header: 'Vini is the best dribler',
      text: 'grab your pizza just time!',
      showModal: false
    }
  },
  methods: {
    handleClick(){
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    },
    toggleModal(){
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
h1{
  color: black;
}
button{
  position: fixed;
  bottom: 800px;
} 
</style>
