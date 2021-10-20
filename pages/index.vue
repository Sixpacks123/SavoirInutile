<template>
  <div class="container">
    <div>
      <h1 class="title">
        SavoirInutile
      </h1>
      <h2 class="subtile" v-on:click="update()">
        {{phrase}}
      </h2>
    </div>
  </div>
</template>

<script>

import axios from 'axios'
export default {
  data(){
    return{
      phrase : "Defautl"
    }
  },methods:{
    update(){
      axios.get('https://uselessfacts.jsph.pl/random.json?language=en').then(reponse => this.phrase  = reponse.data.text)

    }
  },
  mounted(){
    axios.get('https://uselessfacts.jsph.pl/random.json?language=en').then(reponse => this.phrase  = reponse.data.text)
  }
}
</script>
<style>
  .container{
    margin: 0 auto;
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
  }

  .title{
    display: block;
    font-weight: 300;
    font-size: 42px;
    word-spacing: 5px;
    padding-bottom: 15px;
  }

  .links{
    padding-top:15px;
  }
</style>