<template>
  <div>
    <div>the currency exchange rate for USD: <strong>{{usd}}</strong></div>
    <div>the currency exchange rate for EUR: <strong>{{eur}}</strong></div>
  </div>
</template>

<script>
import axios from '../node_modules/axios'

export default {
  name: 'App',
  data(){
    return{
      eur:0,
      usd: 0,
    }
  },
  methods:{
    async getData(){
      await axios.get("https://api.nbp.pl/api/exchangerates/tables/A")
      .then(response =>{
        console.log(response);
        response.data[0].rates.forEach(e => {
          if(e.code == "USD"){
            this.usd = e.mid
          }
          else if(e.code=="EUR"){
            this.eur = e.mid
          }
        });
      })
    }
  },
  mounted(){
    this.getData();
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
</style>
