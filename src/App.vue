<template>
  <div id="app">
    <h1>{{ title }}</h1>
    <div class="operands">
      <input v-model="operand1" type="text" placeholder="Число 1" />
      <input v-model="operand2" type="text" placeholder="Число 2" />
      <h3>Результат: {{ result }}</h3>
    </div>
    <div class="buttons">
      <button @click="result = +operand1 + +operand2">+</button>
      <button @click="result = +operand1 - +operand2">-</button>
      <button @click="result = +operand1 * +operand2">*</button>
      <button @click="result = +operand1 / +operand2">/</button>
      <button @click="result = Math.pow(operand1, operand2)">
        Число 1 в степени числа 2
      </button>
      <button @click="result = Math.floor(+operand1 / +operand2)">
        % (деление без остатка)
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      title: "Калькулятор",
      operand1: "",
      operand2: "",
      result: 0,
    };
  },
};
</script>

<style>
#app {
  display: flex;
  justify-content: center;
  flex-direction: column;
}
h1,
h3 {
  text-align: center;
}
.operands {
  width: 350px;
  margin: 0 auto;
}
.buttons {
  width: 500px;
  margin: 0 auto;
}

button:not(:first-child) {
  margin-left: 5px;
}
</style>
