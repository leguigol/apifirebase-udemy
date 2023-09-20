<template>
        <input 
        type="text" 
        class="form-control my-2"
        placeholder="Ingrese nombre"
        v-model.trim="tarea.nombre"
      >
      <div class="form-check form-check-inline">
        <input class="form-check-input" 
          type="checkbox" 
          id="inlineCheckbox1" 
          v-model="tarea.categorias"
          value="javascript"
        >  
        <label 
            class="form-check-label" 
            for="inlineCheckbox1"
         >Javascript</label>
      </div>
      <div class="form-check form-check-inline">
        <input class="form-check-input" 
          type="checkbox" 
          id="inlineCheckbox2" 
          v-model="tarea.categorias"
          value="Node Js"

        >  
        <label 
            class="form-check-label" 
            for="inlineCheckbox2"
         >Node Js</label>
      </div>
      <div class="mt-2">
        <div class="form-check form-check-inline">
          <input class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio1" value="urgente" v-model="tarea.estado">
          <label class="form-check-label" for="inlineRadio1">Urgente</label>
        </div>
        <div class="form-check form-check-inline">
          <input class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio2" value="relax" v-model="tarea.estado">
          <label class="form-check-label" for="inlineRadio2">Relax</label>
        </div>      
      </div>
      <div class="mt-2">
        <input type="text" v-model.number="tarea.numero" class="form-control"> 
      </div>
      <div class="d-grid">
        <button :disabled="bloquear" @click="procesarFormulario" class="btn btn-dark mt-2 btn-block" type="submit">PROCESAR</button>
      </div>

</template>

<script>
export default {
    props: {
        tarea: Object
    },
    computed: {
        bloquear(){
        return this.tarea.nombre.trim()==="" ? true: false
        }
    }    
}
</script>

<style>

</style>