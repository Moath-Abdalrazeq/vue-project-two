  

<template>
<div class="home" >
  <h2  ref=" appTitleRef">{{appTitle}}</h2>
  <div>{{counterData.title}}:</div>
  <div> 
   <button @click="decreaseCounter(2)" class="btn">--</button>
   <button @click="decreaseCounter(1)" class="btn">-</button>
   <span class="counter">{{ counterData.count }}</span>
    <button @click="increaseCounter(1,$event)" class="btn">+</button>
    <button @click="increaseCounter(2)" class="btn">++</button>
   </div>
   <p>This Counter is  {{oddOrEven}}</p>
   <div class="edit">
    <h4>Edit Counter Title :</h4>
    <input v-model="counterData.title" type="text" v-autofocus>
   </div>
</div>
</template>

<script setup >
  import {ref, reactive ,nextTick, computed , watch } from 'vue'
  import {vAutofocus} from '@/directives/vAutofocus'

const appTitle='My OK Counter App'

 
    const  counterData = reactive({
      count:0,
      title:"My Counter"
    })
    
    watch(()=>counterData.count, (newCount)=>{
      if (newCount===20){
        alert('Way to go! You made it to 20!!')
      }
    })

   const oddOrEven= computed(()=>{
     if(counterData.count %2 === 0) return "even"
     return 'odd'
    })
    const increaseCounter = (amount ,e) => {

    counterData.count += amount
   
    }
   
      const decreaseCounter = amount => {
        if (counterData.count===0) {
          counterData.count =counterData.count
        }else {counterData.count-=amount}
         
    }

 

</script>
 

 
<style scoped>
.home{
 text-align: center;
 padding: 20px;
}

.btn, .counter{
  font-size: 40px;
margin: 10px;
}
.edit{
  margin-top: 60px;
}
</style>