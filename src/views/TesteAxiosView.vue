<template>
    <p>Teste do Axios</p>
    <button @click="buscarEstados">testar!!</button>
    <p v-for="estado in listaEstados" :key="estado.id">{{ estado.nome }}</p>
</template>

<script>
import axios from "axios";
    export default {
        data() {
            return {
                listaEstados:[]
            }
        },
        methods: {
            async buscarEstados() {
                // buscar a lista de estados no servidor
                // http://localhost:8080/estados
                const response = await axios.get("http://localhost:8080/estados")
                console.log(response);
                this.listaEstados = response.data;
            }
        }
    }
</script>