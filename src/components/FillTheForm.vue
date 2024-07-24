<!-- eslint-disable no-undef -->
<script setup>
import { ref, reactive} from 'vue';
const emit = defineEmits(['salvar'])
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
});

const estados = [
  { uf: 'AC', name: 'Acre' },
  { uf: 'AL', name: 'Alagoas' },
  { uf: 'AP', name: 'Amapá' },
  { uf: 'AM', name: 'Amazonas' },
  { uf: 'BA', name: 'Bahia' },
  { uf: 'CE', name: 'Ceará' },
  { uf: 'DF', name: 'Distrito Federal' },
  { uf: 'ES', name: 'Espírito Santo' },
  { uf: 'GO', name: 'Goiás' },
  { uf: 'MA', name: 'Maranhão' },
  { uf: 'MT', name: 'Mato Grosso' },
  { uf: 'MS', name: 'Mato Grosso do Sul' },
  { uf: 'MG', name: 'Minas Gerais' },
  { uf: 'PA', name: 'Pará' },
  { uf: 'PB', name: 'Paraíba' },
  { uf: 'PR', name: 'Paraná' },
  { uf: 'PE', name: 'Pernambuco' },
  { uf: 'PI', name: 'Piauí' },
  { uf: 'RJ', name: 'Rio de Janeiro' },
  { uf: 'RN', name: 'Rio Grande do Norte' },
  { uf: 'RS', name: 'Rio Grande do Sul' },
  { uf: 'RO', name: 'Rondônia' },
  { uf: 'RR', name: 'Roraima' },
  { uf: 'SC', name: 'Santa Catarina' },
  { uf: 'SP', name: 'São Paulo' },
  { uf: 'SE', name: 'Sergipe' },
  { uf: 'TO', name: 'Tocantins' }
];

const mostrarPerfil = ref(true);



function salvarPerfil() {
  // if (LinguagemPreferida.value === '' || dados.Confirmar !== dados.Senha) {
  //   alert('Preencha todos os campos corretamente');
  // } else {
  //   mostrarPerfil.value = false;
    
  // }
emit('salvar', {...dados})
}

</script>
<template>
  <h1>Formulário de cadastro</h1>
  <form @submit.prevent="salvarPerfil" ><div class="row">
          <div class="areas">
            <label for="nome">Insira o seu nome:</label>
            <input type="text" id="nome" v-model="dados.Nome" placeholder="Digite seu nome" required />
          </div>
          <div class="areas">
            <label for="sobrenome">Insira o seu sobrenome:</label>
            <input type="text" id="sobrenome" v-model="dados.Sobrenome" placeholder="Digite seu sobrenome" required />
          </div>
        </div>
        <div class="row">
          <div class="areas">
            <label for="dataNascimento">Insira sua data de nascimento:</label>
            <input type="date" id="dataNascimento" v-model="dados.DataNascimento" required />
          </div>
          <div class="areas">
            <label for="email">Insira o seu email:</label>
            <input type="email" id="email" v-model="dados.Email" placeholder="fulanodetal12@gmail.com" required />
          </div>
        </div>
        <div class="row">
          <div class="areas">
            <label for="endereco">Insira seu endereço:</label>
            <input type="text" id="endereco" v-model="dados.Endereco" placeholder="Rua dos Bobos nº0" required />
          </div>
          <div class="areas">
            <label for="cidade">Cidade:</label>
            <input type="text" id="cidade" v-model="dados.Cidade" placeholder="Joinville" required />
          </div>
          <div class="areas">
            <label for="estado">Estado:</label>
            <select v-model="dados.Estado" id="estado" required>
              <option selected disabled value="">Selecionar...</option>
              <option v-for="estado in estados" :key="estado.uf" :value="estado.uf">{{ estado.name }}</option>
            </select>
          </div>
        </div>
        <div class="row">
          <div class="area">
            <p>Hobbies:</p>
            <input type="checkbox" id="hobbies1" value="esportes" v-model="dados.Hobbies" />
            <label for="hobbies1" >Esportes</label>
            <input type="checkbox" id="hobbies2" value="música" v-model="dados.Hobbies" />
            <label for="hobbies2">Música</label>
            <input type="checkbox" id="hobbies3" value="viagens" v-model="dados.Hobbies" />
            <label for="hobbies3">Viagens</label>
            <input type="checkbox" id="hobbies4" value="leitura" v-model="dados.Hobbies" />
            <label for="hobbies4">Leitura</label>
          </div>
          <div class="area">
            <p>Linguagem preferida:</p>
            <input type="radio" v-model="dados.LinguagemPreferida" value="C" id="langC" />
            <label for="langC">C</label>
            <input type="radio" v-model="dados.LinguagemPreferida" value="Java" id="langJava" />
            <label for="langJava">Java</label>
            <input type="radio" v-model="dados.LinguagemPreferida" value="Python" id="langPython" />
            <label for="langPython">Python</label>
            <input type="radio" v-model="dados.LinguagemPreferida" value="Javascript" id="langJs" />
            <label for="langJs">JavaScript</label>
          </div>
        </div>
        <div class="rows">
          <div class="areas">
            <label for="senha">Insira senha:</label>
            <input type="password" id="senha" minlength="4" v-model="dados.Senha" required />
          </div>
          <div class="areas">
            <label for="confirmSenha">Confirme a sua senha:</label>
            <input type="password" id="confirmSenha" minlength="4" v-model="dados.Confirmar" required />
          </div>
          <div class="row">
            <div class="areas">
              <label for="biografia">Fale um pouco sobre você:</label>
              <input type="text" id="biografia" placeholder="Meu nome é..." />
            </div>
          </div>
        </div>
        <div id="buttons">
          <input type="submit" value="Enviar" >
        </div>
      </form>
      
</template>
<style scoped>

.row {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}

.area {
  margin: 10px;
}

.areas {
  display: flex;
  flex-direction: column;
  margin: 10px;
}

label {
  margin: 2px;
}

input,
select {
  border: solid rgb(128, 128, 128) 2px;
  border-radius: 4px;
  padding: 5px;
}
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