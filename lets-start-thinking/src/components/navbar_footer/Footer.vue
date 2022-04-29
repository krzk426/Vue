<template>
  <footer>
    <div class="footerData">
      <div class="appName">Books List</div>
      <div class="allRightsReserved">&copy; Copyright 2022 HTML.am</div>
    </div>
  </footer>
</template>

<script>
export default {
  data() {
    return {};
  },
};
</script>

<style scoped>
footer {
  background-color: black;
  position: fixed;
  bottom: 0;
  right: 0;
  left: 0;
  width: 100%;
  
}
.footerData {
  padding: 30px 0;
  width: 100%;
  display: flex;
  justify-content: space-around;
  align-items: center;
}
.appName {
  font-weight: 800;
  font-size: 2em;
}
.allRightsReserved {
  font-style: italic;
}
</style>
