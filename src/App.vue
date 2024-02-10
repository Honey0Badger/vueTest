<template>
  <div class="container">
  <h1> Тест Emit и Provide</h1>
    <Card/>
    <div class="rows">
    <button v-on:click="addAnimal" type="button" class="btn btn-primary">Кнопка</button>
    </div>
  </div>
</template>

<script>
import Card from './components/Card.vue'

export default {
  name: 'App',
  components: {
    Card
  },
  provide:{
    animal:"Слон"
  },
  methods:{
    addAnimal(){
      this.animal= 2
    }
  }
}
</script>

<style>

</style>