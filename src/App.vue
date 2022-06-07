<template>
  <h1>Câmbio App</h1>
  <h2>Digite a quantidade de reais e a cotação do dólar:</h2>

  <div>
    <label for="quantidade-reais">Quantidade de Reais</label>
    <input id="quantidade-reais"  v-model="quantidadeReais" v-bind:disabled="resultado">
  </div>

  <div>
    <label for="cotacao-dolar">Cotação do Dólar</label>
    <input id="cotacao-dolar"  v-model="cotacaoDolar" v-bind:disabled="resultado">
  </div>

  <div>
    <button @click="calcular">Caluclar</button>
    <button @click="limpar">Limpar</button>
    <p v-if="resultado">Com {{quantidadeReais}} reais e o dólar a {{cotacaoDolar}} é possível comprar {{resultado}} dólares</p>
  </div>

</template>

<script>

export default {
  data: function() {
    return {
      cotacaoDolar: null,
      quantidadeReais: null,
      resultado: null,
    }
  },

  methods: {
    calcular: function() {
      this.resultado = this.quantidadeReais / this.cotacaoDolar;
    },

    limpar: function() {
      this.cotacaoDolar = null;
      this.quantidadeReais = null;
      this.resultado = null;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
