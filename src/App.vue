<script setup>
import { ref } from 'vue';
import FormsPerfil from './components/FormsPerfil.vue'
import InfoForm from './components/InfoForm.vue'
const sla = ref('')
function salvar(params) {
  console.log(params);
  sla.value = params;
}
</script>

<template>
    <section>
    <FormsPerfil @adicionar="salvar" />

    <InfoForm :user="sla" />
  </section>

</template>

<style scoped>
section {
  display: flex;
  width: 70%;
  margin:  20px auto;
  gap: 2rem;
  }
  
</style>
