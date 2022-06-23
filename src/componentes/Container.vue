<template>

  <section class="src-componentes-container">
    <div id="container">
      <Square v-for="(square, index) in squareQty" :key="index" :color="colors[index]" :pickedColor="
      pickedColor" @selectedColor="selectedColor = $event" />
    </div>

  </section>

</template>

<script lang="js">
import Square from './Square.vue';
export default {
  name: 'container-component',
  components: { Square },
  props: ["squareQty", "colors", 'pickedColor'],
  updated() {
  },
  data() {
    return {
    }
  },
  methods: {
  },
  computed: {
  }
}
</script>

<style scoped lang="css">
#container {
  margin: 20px auto;
  max-width: 600px;
}
</style>