<template>
  <nav>
    <NavbarOptions @optionChoosen="chooseMenuItem" :options="navbarOptions" />
  </nav>
</template>

<script>
import NavbarOptions from "./NavbarOptions.vue";
export default {
  components: {
    NavbarOptions,
  },
  data() {
    return {
      navbarOptions: [
        {
          id: 0,
          title: "add book",
        },
        {
          id: 1,
          title: "books list",
        },
      ],
    };
  },
  methods: {
    chooseMenuItem($event) {
      this.$emit("optionChoosen", $event);
    },
  },
};
</script>

<style>
nav {
  background-color: black;
  position: fixed;
  width: 100%;
  top: 0;
  left: 0;
  right: 0;
}
.navbarBox {
  padding: 30px 0;
}
</style>
