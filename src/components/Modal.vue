<template>
  <div class="backdrop" @click.self="closeModal">
      <div class="modal"  :class="{sale: theam == 'sale'}">
          <h1>{{header}}</h1>
          <p>{{text}}</p>
          <slot>defolt</slot>
          <div class="actions">
          <a href="">it's me</a>
              <slot name="links" class="a"></slot>
          <a href="">it's me</a>

            </div>
      </div>
      </div>

</template>

<script>
export default {
props: ['header', 'text', 'theam'],
methods:{
    closeModal(){
        this.$emit('close')
    }
}
}
</script>

<style scoped>
.modal {
width: 400px;
padding: 20px;
margin: 100px auto;
background: white;
border-radius: 15px;
}

.backdrop {
    top: 0;
    position: fixed;
    background: rgba(0, 0, 0, .5);
    width: 100%;
    height:100%;
}

h1{
    color: #03cfb4;
    border: none;
    padding: 0;
}

.modal .actions{
    text-align: left;
    margin: 40px, 0, 20px, 0;
}

.modal .actions a{
    color: black;
    padding: 8px;
    border: 1px solid #eee;
    border-radius: 4px;
    text-decoration: none;
    margin: 10px;
}

.modal .actions slot{
    color: black;
    padding: 8px;
    border: 1px solid #eee;
    border-radius: 4px;
    text-decoration: none;
    margin: 10px;
}


.modal.sale{
background: crimson;
color: white;
}

.modal.sale h1{
    color: black;
}

.modal.sale .actions{
    color: white;
}
.modal.sale .actions a{
    color: white;
}




</style>