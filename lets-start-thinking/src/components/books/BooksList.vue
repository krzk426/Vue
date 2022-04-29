<template>
  <div>
    <div v-for="(b, index) in books" :key="index" class="book" :class="b.isRead == 'bookRead' ? 'bookRead' : 'bookNotRead'">
      <p>
        <span class="attribute">Title:</span> <span>{{ b.title }}</span>
      </p>
      <p>
        <span class="attribute"> Is Book Read: </span>
        <span v-if="b.isRead == 'bookRead'">yes</span>
        <span v-else>no</span>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "booksList",
  props: ["books"],
  data() {
    return {
      choosenTitle: "",
      isReadOfNewBook: "bookNotRead",
    };
  },
};
</script>

<style>
    .book{
        -webkit-box-shadow: 8px 8px 24px 0px rgba(66, 68, 90, 1);
    -moz-box-shadow: 8px 8px 24px 0px rgba(66, 68, 90, 1);
    box-shadow: 8px 8px 24px 0px rgba(66, 68, 90, 1);
    max-width: 300px;
    padding: 10px 10px 10px 30px;
    margin: 0 auto 2em auto;
    text-align: left ;
    font-weight: 400;
    }
    span{
      font-weight: 400;
    }
    .attribute{
        font-weight: 700;
    }
    .bookRead{
        background-color: #2d6e32;

    }
    .bookNotRead{
        background-color: #d11f55;

    }
</style>