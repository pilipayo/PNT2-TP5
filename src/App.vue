<template>
   <div id="app">
    <Header :pickedColor="pickedColor" />
    <NavBar @isHard="isHard = $event" @squareQty="squareQty = $event" @colors="getColors" @pickedColor="getPicked"
      :message="message" />
    <Container :squareQty="squareQty" :colors="colors" @selectedColor="getSelected" @pickedColor="getPicked"
      @message="getMessage" :pickedColor="pickedColor" />
  </div>
</template>

<script>
import Header from './componentes/Header.vue'
import NavBar from './componentes/NavBar.vue'
import Container from './componentes/Container.vue'

export default {
  name: 'App',
  components: {
    Header,
    NavBar,
    Container
  },
  updated() {
  },
  data() {
    return {
      isHard: false,
      squareQty: 0,
      colors: [],
      selectedColor: '',
      pickedColor: '',
      message: '',
    }
  },
  methods: {
    getColors(e) {
      this.colors = e;
    },
    getSelected(e) {
      this.selectedColor = e;
    },
    getPicked(e) {
      console.log(e);
      this.pickedColor = e;
    },
    getMessage(e) {
      this.message = e;
    }
  }
}
</script>

<style>
html {
  margin: 0;
  all: unset;
}
body {
  margin: 0;
  padding: 0;
  background-color: #232323;
}
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  font-family: "Montserrat", "Avenir";
}
</style>