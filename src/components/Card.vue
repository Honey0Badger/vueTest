<template>
  <div class="rows">
  <slot></slot>
    <div class="row g-3">
      <div class="col-auto">
        <label for="inputName" class="visually-hidden">Название</label>
        <input v-model="part.PName" type="text" class="form-control" id="inputName" placeholder="Название">
      </div>
      <div class="col-auto">
        <label for="inputPrice" class="visually-hidden">Цена за 1 шт.</label>
        <input v-model="part.Price" type="text" class="form-control" id="inputPrice" placeholder="Цена за 1 шт.">
      </div>
      <div class="col-auto">
        <label for="inputVolume" class="visually-hidden">Количество</label>
        <input v-model="part.PVolume" type="text" class="form-control" id="inputVolume" placeholder="Количество">
      </div>
      <div class="col-auto">
        <button v-on:click="added" class="btn btn-primary mb-3">Добавить</button>
      </div>
    </div>
    <button v-on:click="show" class="btn btn-primary mb-3">Посмотреть результат</button>
    <div v-if="check" class="row">
      <ul id="array-rendering">
        <li v-for="item in products" :key="item">
          {{ item.PName }} <br>
          {{ item.Price }} <br>
          {{ item.PVolume }} <br/>
        </li>
      </ul>
    </div>

  <div class="alert alert-primary" role="alert">
    У нас товара лежит в корзине на сумму: {{ this.products.PVolume }}
  </div>

  <slot></slot>
  </div>
</template>

<script>
/* eslint-disable */
import Product from '../Product.js'
export default {
  name: 'Card',
  props: {
    msg: String
  },
  data(){
    return{
      products: [],
      part: Product,
      check: false
    }
  },
  methods:{
    added(){
      this.products.push({...this.part});
    },
    show(){
      this.check = !this.check
    },
    computed: {
      resultSumm(){
        return this.products.length;
        }
    }
  }
}
</script>



<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
