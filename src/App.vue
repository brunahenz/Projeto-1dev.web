<script setup>
import { ref } from 'vue'

const nome = ref('')
const data = ref()
const email = ref('')
const endereco = ref('')
const cidade = ref('')
const estado = ref('')
const hobbie = ref('')
const senha = ref('')
const confirma= ref('')

const ok = ref(false)

</script>

<template>
  
  <button>Nome:</button>
  <input type="text" v-model="nome"  placeholder="Digite seu nome"/>
  <button @click="nome">Enviar</button>
  <hr>
  <button>Data de nascimento:</button>
  <input type="number" v-model="data" placeholder="Digite sua data" />
  <button @click="idade">Enviar</button>
  <hr>
  <button>Email:</button>
  <input type="email" v-model="email" placeholder="Digite seu email"/>
  <button @click="email">Enviar</button>
  <hr>
  <button>Endereço:</button>
  <input type="text" v-model="endereco" placeholder="Digite seu endereço"/>
  <button @click="email">Enviar</button>
  <hr>
  <button>Cidade:</button>
  <input type="text" v-model="cidade" placeholder="Digite sua cidade"/>
  <button @click="email">Enviar</button>
  <hr>
  <label for="estado">Estado:</label>
  <select v-model="estado">
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
  <button>Senha:</button>
  <input type="text" v-model="senha" placeholder="Digite sua senha"/>
  <button @click="nome">Enviar</button>
  <hr>
  <button>Confirmação de senha:</button>
  <input type="text" v-model="confirma" placeholder="Digite sua senha novamente"/>
  <button @click="nome">Enviar</button>
  <hr>
  <button @click="ok = !ok">Mostrar</button>

 
  
</template>
