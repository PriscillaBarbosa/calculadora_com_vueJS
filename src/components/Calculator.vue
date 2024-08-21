<template>
<div class="container mt-5">
    <h2>Calculadora Aritmética</h2>
    <div class="form-group">
    <input
        type="number"
        v-model.number="num1"
        class="form-control"
        placeholder="Número 1"
    />
    </div>
    <div class="form-group">
    <input
        type="number"
        v-model.number="num2"
        class="form-control"
        placeholder="Número 2"
    />
    </div>
    <div class="form-group">
    <select v-model="operation" class="form-control">
        <option value="add">+</option>
        <option value="subtract">-</option>
        <option value="multiply">*</option>
        <option value="divide">/</option>
    </select>
    </div>
    <h3>Resultado: {{ result }}</h3>
</div>
</template>

<script>
export default {
data() {
    return {
    num1: 0,
    num2: 0,
    operation: "add",
    };
},
computed: {
    result() {
    switch (this.operation) {
        case "add":
        return this.num1 + this.num2;
        case "subtract":
        return this.num1 - this.num2;
        case "multiply":
          return this.num1 * this.num2;
        case "divide":
        return this.num2 !== 0
            ? this.num1 / this.num2
            : "Erro: Divisão por zero";
        default:
        return 0;
    }
    },
},
};
</script>

<style scoped>
.container {
max-width: 400px;
}
</style>
