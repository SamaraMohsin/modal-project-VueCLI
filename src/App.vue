<template>
  <h1>{{ title }}</h1>
  <p>Welcome ...</p>
  <div v-if="showModal">
    <!-- <Modal :header="header" :text="text" :header2 ="['sam',4]" theme="sale" @close="toggleModal" /> -->
    <Modal theme="sale nhi bhej rahe abhi" @close="toggleModal" >
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>ninja gateway!</h1>
      <p>Grab your ninja swag for half price!</p>
    </Modal>
  </div>
  <div v-if="showModal2">
    <Modal @close="toggleModal2">
      <h1>Sign up to the newsletter</h1>
    <p>for updates and promo codes!</p>
    </Modal>
    
  </div>
  <button @click.shift="toggleModal">open modal with shift key</button>
  <button @click="toggleModal2">open modal </button>

</template>

<script>
import Modal from './components/Modal'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My First Vue App!',
      // header:'Sign up for a gateway!',
      // text:'Grab your ninja swag for half price!',
      showModal: false,
      showModal2: false
    }
  },
  methods:{
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
  padding-bottom: 10px;
}
</style>