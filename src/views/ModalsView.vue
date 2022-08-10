<template>
 <div class="modals">
<h1> Modals </h1>
<div>
    <label for="">Show dark modals?</label>
    <input v-model="showDarkModals" type="checkbox" >
</div>
 


<button @click="ShowModal = true">Show modal </button>

<component v-model="ShowModal" 
title="My modal title(via prop)"
:is="showDarkModals ? ModalDark : Modal">
   
<p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Aliquam explicabo nemo sapiente suscipit dolores soluta harum. Saepe perspiciatis exercitationem, esse, assumenda debitis ducimus dolorum tempore rem, repellat provident animi ab!</p>
</component>
 </div>
</template>

<script setup>
import {ref} from 'vue'
import Modal from '@/components/Modal.vue'
import ModalDark from '@/components/ModalDark.vue'
/*modals*/
const showDarkModals=ref(false)
const ShowModal = ref(false)

 
</script>


 

 