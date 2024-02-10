<template>
  <div class="formulario">
    <input type="text" v-model="textoTarea" class="input-tarea" />
    <button @click="agregarTarea" class="boton-agregar">Agregar Tarea</button>
  </div>
</template>

<script setup lang="ts">
import { defineEmits , ref } from 'vue'

const emit = defineEmits()

const textoTarea = ref('')

const agregarTarea = () => {
  emit('agregarTarea', textoTarea.value)
  textoTarea.value = ''
}
</script>

<style scoped>
.formulario {
  margin-bottom: 20px;
}

.input-tarea {
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 4px;
  margin-right: 10px;
}

.boton-agregar {
  padding: 8px 16px;
  background-color: #4CAF50;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.boton-agregar:hover {
  background-color: #45a049;
}
</style>

