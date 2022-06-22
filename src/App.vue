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
  font-family: 'Inter', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  padding: 0;
  margin: 0;
}
input {
  font-family: inherit;
  width: 100%;
  padding: 10px;
  border-radius: 6px;
  outline: none;
  border: none;
  font-size: 16px;
  transition: box-shadow 0.1s ease;
}
input:focus {
  box-shadow: 0 0 1px 1px rgba(0, 122, 255);
}
</style>
