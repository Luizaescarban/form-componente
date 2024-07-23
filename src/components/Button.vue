<!-- eslint-disable vue/multi-word-component-names -->

<script setup>
import {reactive} from 'vue'
const dados = reactive({
  Nome: '',
  Sobrenome: '',
  Email: '',
  Endereco: '',
  Senha: '',
  Confirmar: '',
  Cidade: '',
  Estado: '',
  Hobbies: [],
  LinguagemPreferida: []
})


function salvarPerfil() {
  if ( dados.Confirmar !== dados.Senha) {
    alert('Preencha todos os campos corretamente');
  
}}
</script>
<template>
<div class="button">
    <button @click="salvarPerfil" type="submit">Salvar</button>
</div>
    
</template>
<style scoped>
.button {
  display: flex;
  flex-direction: row;
  justify-content: center;
}

button {
  padding: 10px;
  background-color: black;
  color: white;
  border-radius: 5px;
  border: solid black;
}
</style>