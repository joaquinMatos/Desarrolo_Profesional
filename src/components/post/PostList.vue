<template>
    <div>
        <button @click="clicked($event)">clickkaene</button>
        <PostItem 
            @say-hi="clicked($event)"
            v-bind="post"
            v-for="(post,index) in PostData" 
            :key="index"
        />
        
    </div>
</template>
<script lang="ts" setup>
import PostData from '@/data/PostData'
import PostItem from './PostItem.vue'

const clicked = (event:any) =>{
    alert("Hola desde el Padre" + event)
}
</script>

<style scoped></style>