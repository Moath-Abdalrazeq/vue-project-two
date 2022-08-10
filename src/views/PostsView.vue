
<template>
<div class="post-detail">
  <h1>Posts</h1>
  <ul>
    <li v-for="post in posts" :key="post.id">
     <RouterLink :to="'/postDetail/${post.id}'">{{post.title}} </RouterLink>
      </li>
    
   
  </ul>
  <textarea v-autofocus  /> 
   
</div>
</template>

<script setup >
import {ref } from 'vue'
import {vAutofocus } from '@/directives/vAutofocus'


const posts =ref([
  {
    id:'id1',
    title:'post 1'
  },
    {
    id:'id2',
    title:'post 2'
  },
    {
    id:'id3',
    title:'post 3'
  }
])
</script>

<style scoped>
ul{
  margin-bottom:30px
}
</style>