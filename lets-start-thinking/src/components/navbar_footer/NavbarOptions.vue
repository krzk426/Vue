<template>
    <div class="navbarBox">
        <div v-for="(option, index) in options"
        :key="index">
            <div class="menuOption" @click="$emit('optionChoosen', option.id)">{{option.title}}</div>
        </div>
    </div>
</template>

<script>

export default({
    name: "NavbarOptions",
    props: ["options"],
  data() {
    return{
        
    }
    
  },
})
</script>

<style>
.menuOption{
    background-color: #2c3e50;
    padding: 10px 20px;
    color: #000;
    font-weight: 700;
    border-radius: 8px;
    border: 1px black solid;
    max-width: 200px;
    transition: all .5s ease;
margin-right: 2em;
}
.menuOption:hover{
    background-color: #435f7a;
    cursor: pointer;
}
.navbarBox{
  padding: 30px 0;
  display: flex;
  justify-content: flex-end ;
}

</style>
