<script setup>
import { ref } from 'vue'

const nome = ref('')
const idade = ref(0)
const email = ref('')
const ok = true

</script>

<template>
  
  <button>Informe seu nome:</button>
  <input v-model="nome" />
  <button @click="nome">Enviar</button>
  <hr>
  <button>Informe sua idade:</button>
  <input v-model="idade" />
  <button @click="idade">Enviar</button>
  <hr>
  <button>Informe seu email:</button>
  <input v-model="Email" />
  <button @click="Email">Enviar</button>
  <div v-if="ok">Mostrar</div>
  
</template>
