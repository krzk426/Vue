<template>
  <div>
    <Navbar  @optionChoosen="chooseComponent"/>
    <BooksView :choosenComponent="choosenComponent"/>
    <Footer/>
  </div>
</template>

<script>
import BooksView from "./components/books/BooksView.vue";
import Footer from "./components/navbar_footer/Footer.vue"
import Navbar from './components/navbar_footer/Navbar.vue';

export default {
  name: "App",
  components: {
    BooksView,
    Footer,
    Navbar,
  },
  data(){
    return{
       choosenComponent: 0,
    }
  },
  methods:{
    chooseComponent($event){
      this.choosenComponent=$event;
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* background-color: #2c3e50; */
  margin-top: 60px;   
}
body{
  padding: 100px 0;
  background-color: #435f7a;
}
</style>
