 <template>
<teleport to=".modals-container">
  <div class="modal-dark" v-if="modelValue"  >
<h1>{{ title }}</h1>
 
<slot />
 
   <button @click="$emit('update:modelValue',false)">  Hide modal </button>
 </div>  
</teleport>
  </template>
 <script setup>
 /*props*/
const props =defineProps({
  modelValue:{
    type:Boolean,
    default: false
  },
    title:{
    type:String,
    default:'No title specified'
  }
})

 /*Emits*/
  const emit =defineEmits(['update:modelValue' ])

 

 </script>
  
 

 <style scoped>
.modal-dark{
background:#333;
color:white;
padding:10px;
position:absolute;
left:0;
top:0;
width:100%;
height:100%
 
}
</style>