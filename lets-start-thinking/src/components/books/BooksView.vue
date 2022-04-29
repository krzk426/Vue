<template>
<div>
  <BookAdd
  v-if="choosenComponent==0"
  @bookNew="addNewBook"
  
  />
  <BooksList
  v-else
   :books="books"
   />
  </div>
</template>

<script>
import BookAdd from './BookAdd.vue';
import BooksList from './BooksList.vue';
export default {
  components: { BooksList , BookAdd},
  props:["choosenComponent"],
  name: 
    "booksView",
  data() {
    return {
      books: [
        { title: "Thinking, fast and slow", isRead: "bookRead" },
        { title: "Scrum Guide", isRead: "bookNotRead" },
      ],
     
    };
  },
  methods:{
    addNewBook($event){
      console.log("event", $event);
      this.books.push($event.book)
    }
  }
};
</script>

<style scoped>
  div{
    color: #000;
  }
</style>