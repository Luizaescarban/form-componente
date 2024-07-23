<script setup>

import FillTheForm from '@/components/FillTheForm.vue'
import Result from '@/components/Result.vue'
import Button from '@/components/Button.vue'
// cria um objeto reativo que recebe o que vem de salvar
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

</script>

<template>
  <main class="container">
    
<fill-the-form />
<Button></Button>
<result @submit.prevent="salvarPerfil" />
  </main>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  flex-wrap: wrap;
  align-items: center;
  box-shadow: 0px 3px 10px #2c3546;
  border-radius: 15px;
  font-family: Arial, Helvetica, sans-serif;
  margin: 50px 300px;
  padding: 20px 50px;
}
</style>
