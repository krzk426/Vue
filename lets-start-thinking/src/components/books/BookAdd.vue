<template>
  <div>
    <p>Title <br><br> <input type="text" v-model="choosenTitle" /></p>
    <p>
      Is book read <br><br>
      <select v-model="isReadOfNewBook">
        <option value="bookRead">Yes</option>
        <option value="bookNotRead">No</option>
      </select>
    </p>
    <button @click="onAddClick">Add</button>
    <div class="success" v-show="added">
      Książka {{choosenTitle}} została dodana do listy!
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      choosenTitle: "",
      isReadOfNewBook: "bookNotRead",
      added: false,
    };
  },
  methods: {
    onAddClick() {
      this.$emit("bookNew", {book: {title: this.choosenTitle, isRead: this.isReadOfNewBook }})
      this.added = true;
      setTimeout(()=>{this.added=false}, 5000);
    },
  },
};
</script>

<style>
input, select{
  width: 300px;
  padding: 10px;
}
p{
  font-size: 1.25em;

font-weight: 600;
}
button{
  width: 200px;
  padding: 10px;
  border-radius: 8px;
  text-align: center;
  background-color: #2c3e50;
  margin-top: 2em;
  color: #000;
  transition: all .5s ease;
  font-weight: 900;
}
button:hover{
  cursor: pointer;
    background-color: #435f7a;
}
.success{
  padding: 20px;
  color: #000;
  margin: 2em auto;
  width: 400px;
  background-color: #2d6e32;

}
</style>
