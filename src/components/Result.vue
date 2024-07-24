<!-- eslint-disable vue/multi-word-component-names -->
<script setup>
defineProps(['dados'])
</script>
<template>
  <div >
    <h1>Dados do produto</h1>
    <p>Nome: {{ dados.Nome }}</p>
    <p>Sobrenome: {{ dados.Sobrenome }}</p>
    <p>Email: {{ dados.Email }}</p>
    <p>Endereço: {{ dados.Endereco }}</p>
    <p>Senha: {{ dados.Senha }}</p>
    <p>Confirmação: {{ dados.Confirmar }}</p>
    <p>Cidade: {{ dados.Cidade }}</p>
    <p>Estado: {{ dados.Estado }}</p>
    <p>Seus hobbies: {{ dados.Hobbies }}</p>
    <p>Sua linguagem preferida: {{ dados.LinguagemPreferida }}</p>
  </div>
</template>
<style scoped></style>
