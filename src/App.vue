<template>
<div>
  
<h1>{{title}}</h1><br>
<div v-if="showModal">
<Modal :header="hrader" :text="text" :theam="sale" @close='toggalModal'>
<h2>Hi ali</h2>
<p>Lol Fuck u ...</p>
<hr>
<template v-slot:links>
  <a href="#">sign up now</a>
  <a href="#">more info</a>
</template>
</Modal>
</div>
<input type="text" ref="name">
<button @click="handleClick">click me</button>
<br><br><button @click.alt="toggalModal">Open modal (alt)</button><br>


</div>
</template>


<script>
import Modal from './components/Modal.vue'
export default {
  name: 'App',
  data(){
    return{
      title: 'My first application vuejs ;)',
      hrader: 'Sign up for the Giveaway!',
      text: 'Grab your ninja swag for half price!',
      sale: 'salee',
      showModal: false,
  }},
  methods:{
    handleClick(){
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    },
    toggalModal(){
      this.showModal=!this.showModal
    }
  },
  components: { Modal }
 
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
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
