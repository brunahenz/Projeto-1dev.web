<script setup>

import { ref } from 'vue'

const nome = ref('')
const data = ref('')
const email = ref('')
const endereco = ref('')
const cidade = ref('')
const estado = ref('')
const hobbie = ref([])
const linguagem = ref('')
const biografia = ref('')
const senha = ref('')
const confirma = ref('')
const ok = ref(false)
const user = ref({
  avatar: null
})

function handleFileUpload(e) {
  const target = e.target
  if (target && target.files) {
    const file = target.files[0]
    user.value.avatar = URL.createObjectURL(file)
  }
}
function validar() {
  if (senha.value === confirma.value) {
    return true;
  }
  else {
    return false;
  }
}
</script>

<template>
  <form class="form" @submit.prevent="ok = validar()">
    <div class="centro ">
      <input type="file" id="avatarField" @change="handleFileUpload($event)" />
      <label for="">Nome:</label>
      <input type="text" v-on:keypress="ok = false" v-model="nome" required placeholder="Digite seu nome" />
      <hr>
      <label for="">Data de nascimento:</label>
      <input type="date" v-on:keypress="ok = false" v-model="data" placeholder="Digite sua data" />
      <hr>
      <label for="">Email:</label>
      <input type="email" v-on:keypress="ok = false" v-model="email" placeholder="Digite seu email" />
      <hr>
      <label for="">Endereço:</label>
      <input type="text" v-on:keypress="ok = false" v-model="endereco" placeholder="Digite seu endereço" />
      <hr>
      <label for="">Cidade:</label>
      <input type="text" v-on:keypress="ok = false" v-model="cidade" placeholder="Digite sua cidade" />
      <hr>
      <label for="estado">Estado:</label>
      <select v-on:keypress="ok = false" v-model="estado">
        <option value="AC">Acre</option>
        <option value="AL">Alagoas</option>
        <option value="AP">Amapá</option>
        <option value="AM">Amazonas</option>
        <option value="BA">Bahia</option>
        <option value="CE">Ceará</option>
        <option value="DF">Distrito Federal</option>
        <option value="ES">Espírito Santo</option>
        <option value="GO">Goías</option>
        <option value="MA">Maranhão</option>
        <option value="MT">Mato Grosso</option>
        <option value="MS">Mato Grosso do Sul</option>
        <option value="MG">Minas Gerais</option>
        <option value="PA">Pará</option>
        <option value="PB">Paraíba</option>
        <option value="PE">Pernambuco</option>
        <option value="PI">Piauí</option>
        <option value="RJ">Rio de Janeiro</option>
        <option value="RN">Rio Grande do Norte</option>
        <option value="RS">Rio Grande do Sul</option>
        <option value="RO">Rondônia</option>
        <option value="RR">Roráima</option>
        <option value="SC">Santa Catarina</option>
        <option value="SP">São Paulo</option>
        <option value="SE">Sergipe</option>
        <option value="TO">Tocantins</option>
      </select>
      <hr>
      <label for="hobbie">Hobbie:</label>
      <div class="opcao">
        <input type="checkbox" v-model="hobbie" v-on:keypress="ok = false" value="Esporte" /> Esporte
        <input type="checkbox" v-model="hobbie" v-on:keypress="ok = false" value="Video Game" /> Video Game
        <input type="checkbox" v-model="hobbie" v-on:keypress="ok = false" value="Leitura" /> Leitura
        <input type="checkbox" v-model="hobbie" v-on:keypress="ok = false" value="Estudos" /> Estudos
        <input type="checkbox" v-model="hobbie" v-on:keypress="ok = false" value="Viajar" /> Viajar
      </div>
      <hr>
      <label for="">Linguagem de programação:</label>
      <div class="opcao">
        <input type="radio" v-on:keypress="ok = false" v-model="linguagem" value="JavaScript" /> JavaScript
        <input type="radio" v-on:keypress="ok = false" v-model="linguagem" value="Python" /> Python
        <input type="radio" v-on:keypress="ok = false" v-model="linguagem" value="C#" /> C#
        <input type="radio" v-on:keypress="ok = false" v-model="linguagem" value="Php" /> Php
        <input type="radio" v-on:keypress="ok = false" v-model="linguagem" value="SQL" /> SQL
        <input type="radio" v-on:keypress="ok = false" v-model="linguagem" value="R" /> R
        <input type="radio" v-on:keypress="ok = false" v-model="linguagem" value="VBA" /> VBA
      </div>
      <hr>
      <label for="">Biografia:</label>
      <input type="text" v-on:keypress="ok = false" v-model="biografia" style="padding: 30px;"
        placeholder="Digite sua biografia" />
      <hr>
      <label for="">Senha:</label>
      <input type="password" v-on:keypress="ok = false" v-model="senha" minlength="6" placeholder="Digite sua senha" />
      <hr>
      <label for="">Confirmar senha:</label>
      <input type="password" v-on:keypress="ok = false" v-model="confirma" minlength="6"
        placeholder="Digite sua senha novamente" />
      <hr>
      <button type="submit">Mostrar</button>
    </div>
  </form>
  <div v-if="ok" class="centro">
    <p>O nome digitado é: {{ nome }}</p>
    <p>A data digitada é: {{ data }}</p>
    <p>O email digitado é: {{ email }}</p>
    <p>O endereço digitado é: {{ endereco }}</p>
    <p>A cidade digitada é: {{ cidade }}</p>
    <p>O estado digitado é: {{ estado }}</p>
    <p>O hobbie digitado é: {{ hobbie }}</p>
    <p>A linguagem digitada é: {{ linguagem }}</p>
    <p>A biografia digitada é: {{ biografia }}</p>
    <p>A senha digitada é: {{ senha }}</p>
    <p>A confirmação digitada é: {{ confirma }}</p>
    <img :src="user.avatar" />
  </div>
</template>

<style scoped>
button {
  font-weight: bold;
  color: blue;
}

.centro {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 0 auto;
  margin-top: 3%;
  background-color: rgb(128, 49, 49);
  border-radius: 10px;
  width: 50%;
  color: aliceblue;
  background-image: linear-gradient(to right, rgb(128, 49, 49), black);
}

.opcao {
  display: flex;
}
</style>
