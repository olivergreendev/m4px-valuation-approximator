<template>
  <div id="app">
    <PriceCalculator />
  </div>
</template>

<script>
import PriceCalculator from './components/PriceCalculator.vue'

export default {
  name: 'App',
  components: {
    PriceCalculator
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@100;200;300;400;500;600;700;800;900&display=swap');

*,
::before,
::after {
  box-sizing: border-box;
}

body {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  background-color: #f4f7f9;
}

#app {
  font-family: 'Roboto', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  padding: 0;
  margin: 0;
}

.input-wrapper {
  border: 2px solid;
  display: flex;
  align-items: center;
}

.input-wrapper .vehicle-condition {
  width: 65px;
  height: 65px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 28px;
}

.input-wrapper .input-prefix {
  width: 65px;
  height: 65px;
  background-color: #1a3889;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
  font-weight: 600;
  color: yellow;
}

.input-wrapper .input-prefix.static {
  color: white;
}

.input-wrapper .currency-symbol {
  width: 65px;
  height: 65px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 32px;
  font-weight: 600;
  background-color: white;
}

input {
  font-family: inherit;
  width: 100%;
  padding: 10px 10px 10px 0;
  outline: none;
  border: none;
  font-size: 32px;
  height: 65px;
  color: inherit;
  transition: box-shadow 0.1s ease;
}

input[disabled] {
  background-color: white;
}

.logo .purple {
  color: #40003f;
}

.logo .gray {
  color: #4c4c4c;
}
</style>
