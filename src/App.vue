<script setup>
import { ref } from 'vue'

const nome = ref('')
const idade = ref('')
const email = ref('')
</script>
<template>
  <input type="text" v-model="nome" />
  <p>Nome: {{ nome }}</p>

  <input type="number" v-model="idade" />
  <p>Idade: {{ idade }}</p>

  <input type="email" v-model="email" />
  <p>E-mail:</p>
</template>
