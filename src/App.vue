<script>
export default {
  data() {
    return {
      people: "",
      count: "",
      valor_gorjeta: "",
    };
  },
  methods: {
    calcular() {
      const people = this.people;
      const count = this.count;
      const valor_gorjeta = this.valor_gorjeta;
      let valor_valor_gorjeta = 0;
      let resultado = {};
      valor_valor_gorjeta = count * (valor_gorjeta / 100.0);
      resultado = (count + valor_valor_gorjeta) / people;
      document.getElementById("resultado").innerHTML = resultado;
    },
  },
};
</script>

<template>
  <body oi>
    <main>
      <div class="conteudo-oi">
        <h1>Calculadora de gorjetas</h1>
        <label>
          <p>Qual o valor da conta?</p>
          <input type="number" v-model="count" id="conta" />
        </label>

        <label>
          <p>Qual foi a qualidade do serviço?</p>
          <select oi v-model="valor_gorjeta">
            <option value="30">30% (Excepcional)</option>
            <option value="25">25% (Muito bom)</option>
            <option value="20">20% (Bom)</option>
            <option value="15">15% (Ok)</option>
            <option value="10">10% (Ruim)</option>
            <option value="5">5% (Péssimo)</option>
          </select>
        </label>

        <label
          ><p>Quantas pessoas estão dividindo a conta?</p>
          <input type="number" v-model="people" id="people" />
        </label>
        <button type="button" @click="calcular">Calcular</button>
        <hr />
        <span id="resultado">Valor da Conta</span>
      </div>
    </main>
  </body>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Archivo+Black&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Great+Vibes&display=swap");
h1 {
  color: #000000;
  font-family: "Lucida Sans", "Lucida Sans Regular", "Lucida Grande",
    "Lucida Sans Unicode", Geneva, Verdana, sans-serif;
  font-size: 50px;
}
main {
  background-color: #acd9ec;
  padding: 60px;
  border-radius: 20px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
button {
  background-color: #000000;
  border: #1a5974;
  color: white;
  height: 30px;
  width: 100px;
  border-radius: 10px;
  margin: 10px;
}
input {
  border-color: #1a5974;
  border-radius: 20px;
}
select {
  border-radius: 30px;
  border-color: #1a5974;
}
h2 {
  font-family: "Great Vibes", cursive;
  font-size: 35px;
}
</style>
