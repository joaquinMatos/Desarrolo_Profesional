<template>
    <div class="card">
        <span>
            <h4>{{ props.id }}</h4>
            <h4>{{ props.date }}</h4>
        </span>
        <h1>{{ props.title }}</h1>
        <p>{{ props.body }}</p>
        <button @click="clicked()">clickkaene</button>
        <input type="text" v-model="titulo"/>
    </div>
</template>
<script lang="ts" setup>
import type { IPost } from '@/Interfaces/IPost';
import { ref } from'vue'

const props  = defineProps<IPost>();
const emits = defineEmits(['sayHi'])
const titulo = ref('')
const copia = props;

//Funciones

const clicked = () =>{
    emits('sayHi',props.id)
}

</script>

<style scoped>
.card{
    border: 2px solid red;
    margin: 10px;
}
</style>