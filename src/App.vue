<script setup>
import { computed, ref } from 'vue'

const nome = ref('');
const idade = ref('');
const email = ref('');
const mensagem = ref(false);

function validarforms() {
  if (idade.value < 18 || idade.value > 60) {
    alert("A idade deve ser entre 18 e 60 anos");
    return false;
  }
  if (!email.value.includes("@")) {
    alert("O e-mail deve ser válido.");
    return false;
  }
  return true;
}
function enviarforms() {
  if (validarforms()) {
    mensagem.value = true;
  }
}
</script>
<template>
  <input type="text" v-model="nome" maxlength="20" minlength="3">
  <p>Nome: {{ nome }}</p>

  <input type="number" v-model="idade">
  <p>Idade: {{ idade }}</p>

  <input type="email" v-model="email">
  <p>E-mail: {{ email }}</p>

  <button @click="enviarforms">Enviar</button>
  <p v-if="mensagem"> Dados enviados:</p>
  <ul v-if="mensagem">
    <li>Nome: {{ nome }}</li>
    <li>Idade: {{ idade }}</li>
    <li>E-mail: {{ email }}</li>
  </ul>

</template>
