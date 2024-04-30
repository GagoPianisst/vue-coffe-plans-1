<template>
<div ref="plansWrapper" 
      class="plans">

      <plan-picker-item
       @select="printSelected"
       :selectedPlan="selectedPlan"
       v-for="plan in plans"
      :name="plan"
      v-bind:key="plan"/>  
      <p style="font-size: 25px;">Tiempo: {{ counter }}</p>
    </div>
</template>

<script setup>
import {ref, onMounted, onUnmounted} from 'vue';
import planPickerItem from './plan-picker-item.vue';
 const plans = ref([
    "El soltero",
    "El adicto",
    "El viajero"
    ]);
    const plansWrapper = ref(null);

    const selectedPlan = ref(null);

    const printSelected = (playload) => {
      selectedPlan.value= playload;
    }

    // Creando una referencia reactiva para un contador
    const counter = ref(0);
    // Creando un metodo para incrementar el contador
    const processId = setInterval(() => {
      console.log('Incrementando Contador')
      counter.value++;
    }, 1000);

    //Registrando el CB onMounted
    onMounted(() => {
    console.log('Componente Plan Piker montado');
    });

    // Registrando el CB de OnMount
    onUnmounted(() => {
      console.log('Componente Plan Piker desmontado');
      clearInterval(processId)
    })
</script>

