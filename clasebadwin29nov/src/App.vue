<script setup>

import TaskComponent from '@/components/TaskComponent.vue';
import { ref} from 'vue';


const task = ref(['Estudiar' , 'Sacar 5', 'Descansar'])

function deleteTask(index){
  //console.log('Borrar hijo', index)
  task.value.splice(index,1)
}


</script>

<template>

<div class="bg-gray-50 w-96 shadow-md rounded mx-auto mt-12 px-4 py-3">
  <h1 class="text-2xl font-semibold">Tareas</h1>

  <div class="flex mt-2">
    <input class="rounded-r-none w-4/5 h-8 px-2 border rounded-md py-1 border-green-600" type="text">
    <span class="hover:bg-green-700 hover:cursor-pointer rounded-l-none w-1/5 h-8 text-xl rounded bg-green-500 text-center text-white">+</span>
  </div>

  <TaskComponent v-for="(objeto, index) in task" :key="index" :tarea="objeto" :index="index" @borrarTarea="deleteTask">
 
  </TaskComponent>

</div>
</template>

