<template>
  <div class="rows">
    <form class="row g-3">
      <div class="col-auto">
        <label for="inputName" class="visually-hidden">Название</label>
        <input v-model="part" type="text" class="form-control" id="inputName" placeholder="Название">
      </div>
      <div class="col-auto">
        <label for="inputPrice" class="visually-hidden">Цена за 1 шт.</label>
        <input v-model="price" type="text" class="form-control" id="inputPrice" placeholder="Цена за 1 шт.">
      </div>
      <div class="col-auto">
        <label for="inputVolume" class="visually-hidden">Количество</label>
        <input v-model="volume" type="text" class="form-control" id="inputVolume" placeholder="Количество">
      </div>
      <div class="col-auto">
        <button v-on:click="added" class="btn btn-primary mb-3">Добавить</button>
      </div>
    </form>

    <button v-on:click="show" class="btn btn-primary mb-3">Посмотреть результат</button>

    <div v-if="check" class="row">
      <ul id="array-rendering">
        <li v-for="item in product" :key="item.PName">
          {{ item.PName }} <br>
          {{ item.Price }} <br>
          {{ item.PVolume }} <br>
          
        </li>
      </ul>
    </div>

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
      product: [],
      part: "",
      price: "",
      volume: "",
      check: false
    }
  },
  methods:{
    added(){
      let p = new Product(this.part, this.price, this.volume)
      this.product.push(p)
      alert(this.product[0].PName)
      console.table(this.product)
    },
    show(){
      this.check = true
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
