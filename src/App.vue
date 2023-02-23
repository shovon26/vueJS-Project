<template>
  <h1>{{title}}</h1>
  <teleport to=".modals" v-if="showModal">
    <Modal theme="sale" @click="toggleModal">
      <template v-slot:links>
        <a href="#">Sign up</a>
        <a href="#">learn more</a>
      </template>
      <h1>Vini is the best dribler</h1>
      <p>grab your pizza just time!</p> 
    </Modal>
  </teleport>
  <!-- Reuse component modal -->
  <teleport to=".modals" v-if="showModal2">
    <Modal theme="sale" @click="toggleModal2">
      <template v-slot:links>
        <a href="#">Sign up</a>
        <a href="#">learn more</a>
      </template>
      <h1>Sign up to meet vini</h1>
      <p>this is vinicious jr</p> 
    </Modal>
  </teleport>
  <br><br><br><br>
  <button @click="toggleModal">ShowModal</button>
  <button @click="toggleModal2">ShowModal2</button>


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
      showModal: false,
      showModal2: false 
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
    },
    toggleModal2(){
      this.showModal2 = !this.showModal2
    }
  }
}
</script>

<style>
#app, .modals {
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
/* button{
  position: fixed;
  bottom: 800px;
} */
</style>