<template>
    <div class="person">
      <h2>{{person.name}}</h2>
      <h2>{{person.age}}</h2>
      <button @click=changeAge>点我age</button>
      <button @click=changeName>点我名字</button>
    </div>
  </template>
  
  <script lang="ts">
      export default {
          name:'Person'
      }
  </script>
  
  <script lang="ts" setup>  
  import {reactive,watch} from 'vue'
  
  let person = reactive({
      name:'张三',
      age:18
  })
  function changeAge(){
    person.age += 1
  }

  function changeName(){
    person.name += '~'
  }

  watch(person,(newvalu,oldvalue)=>{
    console.log(newvalu.name,oldvalue?.name);
    
  })
  
</script>

<style scoped>

.person{
    background-color: pink;
    box-shadow: 0 1px 10px;
    border-radius: 10px;
    padding: 20px;
}

</style>