<template>
    <div>
        <button @click="clicked">clickkaene</button>
        <PostItem 
            @say-hi="clicked()"
            v-bind="post"
            v-for="(post,index) in PostData" 
            :key="index"
        />
        
    </div>
</template>
<script lang="ts" setup>
import PostData from '@/data/PostData'
import PostItem from './PostItem.vue'

const clicked = () =>{
    alert("Hola desde el Padre")
}
</script>

<style scoped></style>