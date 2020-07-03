<template>
  <div id="app">
    <h1>Conversor de Moedas</h1>
      <div class="grid">
          <Conversor moeda-a="USD" moeda-b="BRL" />
          <Conversor moeda-a="BRL" moeda-b="USD" />
      </div>

      <div class="grid">
          <Conversor moeda-a="CAD" moeda-b="BRL" />
          <Conversor moeda-a="BRL" moeda-b="CAD" />
      </div>

      <div class="grid">
          <Conversor moeda-a="EUR" moeda-b="BRL" />
          <Conversor moeda-a="BRL" moeda-b="EUR" />
      </div>
   
  </div>
</template>

<script>
import Conversor from "./components/Conversor";

export default {
  name: 'App',
  components: {
    Conversor
  }
};
</script>

<style>
body {
  background-color: #4297bd;
}

#app {
  margin: auto;
  width: 900px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1 {
  color: #ffffff;
  text-transform: uppercase;
  letter-spacing: 2px;
}

.grid {
  display: flex;
  margin-top: 40px;
  justify-content: space-around;
  align-items: center;
}
</style>
