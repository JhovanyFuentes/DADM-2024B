<template>
    <div @click="selectPlan" class="plan">
      <div class="description">
        <span class="title">{{ name }} {{ isSelected ? '😊' : ''}}
        </span>
      </div>
    </div>
  </template>
  
  <script setup>
  //Importamos la funcion para crear propiedad computada
   import {computed} from 'vue';
//*********************************************************** */
//Importacion de la funcion ref
//import { ref } from 'vue';
//*********************************************************** */

// Usando un macro para definir las props
//defineProps(['name', 'planIcon']);
const props = defineProps({
  name :{
  type : String,
  requiered : true,
},
selectPlan:String
})
//Definir un event
const emit = defineEmits(['select'])

//*********************************************************** */
//Variable que permite recordar si el plan ha sido seleccionado
//const selected = ref(false)
//*********************************************************** */

// Funcion que permite cambiar el estado de la variable
const selectPlan = () => {
//*********************************************************** */
  //selected.value = true;
//*********************************************************** */

  //Plan ha sido seleccionado
  emit ('select', props.name);
};
//Creando una propiedad computada para saber si el plan ha sido seleccionado
const isSelected = computed(()=>{
  return props.name===props.selectPlan;

})
  </script>
 
  
  <style scoped>
  
  </style>