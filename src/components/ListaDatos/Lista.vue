<template>
  <div>
    <h1>Lista de Tareas</h1>
    <Formulario @agregarTarea="agregarTarea" />
    <ul>
      <li v-for="(tarea, index) in tareas" :key="tarea.id" :style="{ color: tarea.colorTexto, backgroundColor: tarea.colorFondo }" @click="seleccionarTarea(index)">
        {{ tarea.texto }}
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import Formulario from './tareas.vue'

const tareas = ref<{ id: string, texto: string, colorTexto: string, colorFondo: string }[]>([])

const agregarTarea = (texto: string) => {
  if (texto !== null && texto.trim() !== '') {
    const tareaExistente = tareas.value.find(t => t.texto === texto)
    if (!tareaExistente) {
      const nuevaTarea = {
        id: Date.now().toString(),
        texto: texto,
        colorTexto: 'black',
        colorFondo: 'white'
      }
      tareas.value.push(nuevaTarea)
    }
  }
}

const seleccionarTarea = (index: number) => {
  tareas.value.forEach((tarea, i) => {
    if (i === index) {
      tarea.colorTexto = 'white'
      tarea.colorFondo = 'blue'
    } else {
      tarea.colorTexto = 'black'
      tarea.colorFondo = 'white'
    }
  })
}
</script>
