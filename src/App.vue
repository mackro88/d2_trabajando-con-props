<template>
  <div id="app">
    <h2>Listado de pendientes</h2>
    <div>
      <h3>Agregar tarea</h3>
      <input type="text" v-model="addToTareas" placeholder="ej. Cocinar" @keyup.enter="addItem" /><button @click="addItem">Añadir</button>
    </div>
    <listado :tareas="tareas" @removeItems="removeItems"/>
  </div>
</template>

<script>
import Listado from './components/Listado.vue'

export default {
  name: 'App',
  components: {
    Listado,
  },
  data: ()=> ({
    tareas: ["Soy un ejemplo, bórrame"],
    addToTareas: "",
  }),
  methods: {
    addItem(){
      if (this.addToTareas != "") {
        this.tareas.push(this.addToTareas)
        this.addToTareas = "";
      }
    },
    removeItems(index){
        this.tareas.splice(index,1)
    }
  }
}
</script>

<style scoped>
  button{
      border: none;
      background:teal;
      color: whitesmoke;
      border-radius: 5%;
      padding: 3px 7px 3px 7px;
      margin-left: 0.1rem;
  }
  button:hover{
      background:darkslategrey;  
  }
</style>
