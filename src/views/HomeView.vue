<template>
  <div class="home">
    <form @submit.prevent="procesarFormulario">
      <Input :tarea="tarea" />
    </form>
    <hr>

    <ListaTareas />
  </div>
</template>

<script>
import ListaTareas from '@/components/ListaTareas.vue';
import { mapActions } from 'vuex';
import Input from '../components/Input.vue';

const shortid=require('shortid');

export default {
  name: 'HomeView',
  components: {
    Input,
    ListaTareas
  },
  data() {
    return {
      tarea: {
        id: '',
        nombre: '',
        categorias: [],
        estado: '',
        numero: 0
      }  
    } 
  },
  methods: {
    ...mapActions(['setTareas']),
    procesarFormulario(){
      console.log(this.tarea);
      if(this.tarea.nombre.trim()===""){
        console.log('campo vacio');
        return;
      }
      console.log('no esta vacio');
      // enviar datos
      // generar id
      this.tarea.id=shortid.generate();
      // console.log(this.tarea.id);

      this.setTareas(this.tarea)

      this.tarea={
        id: '',
        nombre: '',
        categorias: [],
        estado: '',
        numero: 0

      }

    }
  }  
}
</script>
