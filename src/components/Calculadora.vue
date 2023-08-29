<script>

const dados = {
    valor1: '',
    valor2: '',
    operador: '+'
}

export default {
    data() {
        return dados;
    },
    methods: {
        resultadoCalculo() {
            const numero1 = Number(this.valor1);
            const numero2 = Number(this.valor2);
            const operacao = {
                '+': numero1 + numero2,
                '-': numero1 - numero2,
                '*': numero1 * numero2,
                '/': numero1 / numero2
            }
            return operacao[this.operador];
        }
    }
}
</script>


<template>
    <div class="container">
        <header class="p-5 mb-4 mt-4 bg-info rounded-4">
            <h1 class="mb-3 mt-5">Calculadora</h1>
            <input class="me-2" type="number" v-model="valor1" @input="resultadoCalculo" />
            <select class="me-2" v-model="operador" @change="resultadoCalculo">
                <option value="+">+</option>
                <option value="-">-</option>
                <option value="*">*</option>
                <option value="/">/</option>
            </select>
            <input type="number" v-model="valor2" @input="resultadoCalculo" />
            <p class="mt-3">Resultado: {{ resultadoCalculo() }}</p>
        </header>
    </div>
</template>