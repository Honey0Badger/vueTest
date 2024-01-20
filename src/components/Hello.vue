<template>
  <div class="hello">
    <div class="card" style="width: 18rem;">
    <img v-if="openImg" v-bind:src="foto" class="card-img" alt="">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">{{msg}}</p>
        <p class="card-text">{{descr}}</p>
        <button v-on:click="remove" type="button" class="btn btn-danger">{{msgBtn}}</button>
      </div>
    </div>
  </div>
</template>

<script>
/* eslint-disable */
export default {
  name: 'Hello',
  props: {
    msg: String,
    descr: String,
    foto: String,
    view: Boolean
  },
  data(){
    return{
      openImg: true,
      msgBtn: "Ликвидировать"
    }
  },
  methods:{
    remove(){
      this.openImg = !this.openImg
      if(this.openImg):{
        this.msgBtn = "Ликвидировать"
      }else{
        this.msgBtn="Восстановить"
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
