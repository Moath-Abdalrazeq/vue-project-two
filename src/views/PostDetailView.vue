<template>
<div class="Post-detail">
    <h1>This is Post page </h1>
    <p> Display the content of post with ID of {{$route.params.id}}</p>
    <div> 
        <button @click="showPostId">Show Post ID</button>
    </div>
       <div> 
        <button @click="goHomein3sec ">Go Home in 3 sec</button>
    </div>
      <div> 
        <button @click="goToFirstPage ">Go To first post</button>
    </div>

    <p><RouterLink to="/posts">&lt; Back</RouterLink> </p>
     
    </div> 
</template>

<script setup>
import { useRoute,useRouter } from 'vue-router'
const route = useRoute() 
const router = useRouter()   
 const showPostId =()=>{
alert('The ID of this post is: ${ route.params.id}')
 }

 const goHomein3sec =()=>{
    setTimeout(() => {
       router.push({name:'home'})
    }, 3000)
 }

 const goToFirstPage =()=>{
    router.push({
    name:'postDetail',
    params:{
        id:'id1'
    }
    })
 }
</script>