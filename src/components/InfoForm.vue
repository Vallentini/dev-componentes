<script setup>
  defineProps(['user']);
</script>
<template>
  <div class="resultado">
    <h1>Informações</h1>
        <p>Nome: {{ user.nome }}</p>
        <p>Sobrenome: {{ user.sobrenome }}</p>
        <p>Email: {{ user.email }}</p>
        <p>Data de nascimento: {{ user.data }}</p>
        <p>Endereço: {{  user.endereco }}</p>
        <p>Cidade: {{  user.cidade }}</p>
        <p>Estado: {{  user.estado }}</p>
        <p>Rua: {{ user.rua }}</p>
        <p>Bairro {{ user.bairro }}</p>
        <p>Biografia:{{  user.biogafria }}</p>
        <p>Hobbies: {{  user.hobbies }}</p>
        <p>Linguagem:{{  user.linguagempref }}</p>
  </div>
</template>

<style scoped>
.resultado{
  width: 40%;
  height: 500px;
  margin: auto;
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-top: 20px;
  margin-bottom: 20px;
  padding-left: 30px;
  justify-content: center;
  align-items: left;
  font-family: "Lobster", sans-serif;
  font-weight: 400px;
  color: white;
  border-radius: 20px;
  font-style: normal;
  background-color:rgba(7, 30, 73, 0.507);   
}

</style>