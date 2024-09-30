<script setup>
import { ref } from 'vue'
const header = ref('App lista de compras')
const items = ref([
  { id: '1', label: '10 bolillos' },
  { id: '2', label: '1 lata de frijoles' },
  { id: '3', label: '1 chela' },
  { id: '4', label: '1 nutella' },
  { id: '5', label: '1 lata de atun' },
  { id: '6', label: '1 pc gamer' }
])
const newItem = ref('')
const newItemPriority = ref('low');
const newItemHighPriority = ref(false);
</script>

<template>
  <h1>
    <!--agregamos un icono al codigo a un costado del header-->
    <i class="material-icons shopping-cart-icon">local_mall</i>
    {{ header }}
  </h1>
  <input type="text" placeholder="Add Item" v-model.trim="newItem">
<!-- Radio Buttons -->
<label>
  <input type="checkbox" v-model="newItemHighPriority">Alta Prioridad
</label>
{{ newItem }}
...

  {{ newItemHighPriority == '' ? 'true' : 'false'}}
  <!--ul>li*3 es el lenguaje emet a usar-->
  <ul>
    <li v-for="item in items" :key="item.id">🛒 {{ item.label }}</li>
  </ul>
</template>

<style scoped>
.shopping-cart-icon {
  font-size: 2rem;
}
</style>
