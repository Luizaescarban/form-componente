<!-- eslint-disable vue/multi-word-component-names -->
<script setup>
import {defineProps} from 'vue'
const props = defineProps(['dados']);

</script>
<template>
    <div v-for="dado in props.dados" :key="dado.id">  
     <h1>Dados do produto</h1>
    <p>Nome: {{ dado.Nome }} </p> 
    <p>Sobrenome: {{ dado.Sobrenome }}</p>
    <p>Email: {{ dado.Email }}</p>
    <p>Endereço: {{ dado.Endereco }}</p>
    <p>Senha: {{ dado.Senha }}</p>
    <p>Confirmação: {{ dado.Confirmar }}</p>
    <p>Cidade: {{ dado.Cidade }}</p>
    <p>Estado: {{ dado.Estado }}</p>
    <p>Seus hobbies: {{ dado.Hobbies }}</p>
    <p>Sua linguagem preferida: {{ dado.LinguagemPreferida }}</p></div>
  
</template>
<style scoped>

</style>