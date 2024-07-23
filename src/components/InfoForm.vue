<script setup>
</script>
<template>
<section v-if="mostrarPerfil">
          <div>
            <p v-for="(value, key) of user" :key="key">{{ key }}: {{ value }}</p>
          </div>
          <button @click="mostrarPerfil = false">Esconder</button>
        </section>
</template>
<style scoped>
</style>
