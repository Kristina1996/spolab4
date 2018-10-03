<template>
  <div id="app">
    <img width="25%" src="./assets/logo.png">
    <HelloWorld/>

    <div class="form__field">
      <div class="form__label">
        <strong>Please choose a color:</strong>
      </div>
    <div class="form__input">
      <swatches v-model="color" :colors="colors" @input="getColor" row-length="5" popover-to="left">
        <slot="trigger" :value="color" class="form__input__element" readonly>
      </swatches>
    </div>
</div>

  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import Swatches from 'vue-swatches';

export default {
  name: "App",
  components: {
    HelloWorld,
    Swatches
  },
  data () {
    return {
      color: '#b9f5f1',
      colors: [
        ['#F64272', '#F6648B', '#F493A7', '#F891A6', '#FFCCD5' ],
        ['#8b5aff', '#a27bff', '#b99cff', '#d0bdff', '#e8deff' ],
        ['#51e5db', '#74ebe3', '#96f0ea', '#b9f5f1', '#dcfaf8' ],
        ['#ffa51a', '#ffb748', '#ffc976', '#ffdba3', '#ffedd1' ]
      ]
    }
  },
  methods: {
    getColor: function (color) {
        var newcolor = color;
        console.log(color);
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
