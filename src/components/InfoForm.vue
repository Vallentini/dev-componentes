<script setup>
  defineProps(['form']);
</script>
<template>
  <div class="resultado">
    <h1>Informações</h1>
        <p>Nome: {{ user.nome }}</p>
        <p>Email: {{ user.email }}</p>
        <p>Data de nascimento: {{ user.data }}</p>
        <p>Endereço: {{  user.endereco }}</p>
        <p>Cidade: {{  user.cidade }}</p>
        <p>Estado: {{  user.estado }}</p>
        <p>Rua: {{ user.rua }}</p>
        <p>Bairro {{ user.bairro }}</p>
        <p>Hobbies: {{  user.hobbies }}</p>
        <p>Linguagem:{{  user.linguagempref }}</p>
        <p>Biografia:{{  user.bio }}</p>
  </div>
</template>

<style scoped>

</style>