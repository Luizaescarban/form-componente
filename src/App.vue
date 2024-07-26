<script setup>
import FillTheForm from '@/components/FillTheForm.vue'
import Result from '@/components/Result.vue'

// cria um objeto reativo que recebe o que vem de salvar
import { ref, reactive } from 'vue'
const MostrarPerfil = ref(false)
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
function salvar(item) {
  Object.assign(dados, item)
  MostrarPerfil.value = true
}
</script>

<template>
  <main class="container">
    <result v-if="MostrarPerfil === true" :dados="dados" />
    <fill-the-form @salvar="salvar" v-else />
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
