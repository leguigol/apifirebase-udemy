<template>
  <!-- <H1>EDITAR {{ $route.params.id }} - {{ tarea }}</H1> -->
  <form @submit.prevent="updateTarea(tarea)">
    <Input :tarea="tarea" />
  </form>
</template>

<script>
import { mapState, mapActions } from 'vuex';
import Input from '../components/Input.vue';

export default {
  computed: {
    ...mapState(['tarea'])
  },
  methods: {
    ...mapActions(['setTarea','updateTarea'])
  },
  created(){
    this.setTarea(this.$route.params.id);
  },
  components: {
    Input
  }
}
</script>

<style>

</style>