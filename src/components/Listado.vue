<template>
    <div>
        <h3>Tareas a realizar</h3>
        <ul id="todoList">
            <li v-for="(tarea, index) in tareas" :key="index">{{tarea}}
            <button type="submit" @click="$emit('removeItems', index)">Eliminar</button></li>
        </ul>
    </div>
</template>
<script>

export default {
  name: 'Listado',
  data: () => ({
  }),
  props: {
    tareas: {
        type: Array,
        required: true,
      }
  },

}
</script>

<style scoped>
  ul {
      list-style-type:circle ;
  }
  button{
      border: none;
      background:crimson;
      color: whitesmoke;
      border-radius: 5%;
      padding: 3px 7px 3px 7px;
      margin-left: 1rem;
      font-size: 0.7rem;
  }
  button:hover{
      background:darkred;  
  }
</style>