<template>
  <div v-if="producto" class="card" style="width: 50%">
    <img :src="producto.imagen" class="card-img-top" alt="" />
    <div class="card-body">
      <h5 class="card-title">{{ producto.nombre }}</h5>
      <p class="card-text">
        {{ producto.descripcion }}
      </p>
       <router-link to="/">
      <button class="btn btn-primary">Volver</button> 
      </router-link>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    producto: Object,
  },
};
</script>
