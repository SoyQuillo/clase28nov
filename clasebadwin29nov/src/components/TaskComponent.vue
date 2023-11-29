<script setup>

const props = defineProps({
    tarea: {
        type:String,
        default: 'Tarea indefinida'
    },
    index:{
        type: Number
    }
})

const emmit = defineEmits(['borrarTarea'])

function borrarTarea(index){
    //console.log('Borrar tarea', index)

    emmit('borrarTarea', index)
}

</script>

<template>

<div class="flex justify-between bg-gray-200 rounded px-4 py-1 mt-1">
    {{ props.tarea }}
    <span class="hover:bg-red-600 hover:cursor-pointer rounded bg-red-400 text-center text-white px-2" @click="borrarTarea(props.index)">X</span> 
  </div>

</template>