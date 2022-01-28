<template>
    <div class="d-flex justify-content-center mt-5 ms-5 me-5">
   <TarjetaProducto
      v-for="producto in productos" 
      :key="producto.id" 
      :producto="producto"
   />
  </div>
</template>

<script>
import TarjetaProducto from '@/components/TarjetaProducto.vue'
import ServiciosProductos from "@/servicios/ServiciosProductos.js"


export default {
  name: "ListaProductos",
  components: {
    TarjetaProducto
  },
  data() {
    return {
      productos: null,
    };
  },
  created () {
   ServiciosProductos.obtenerProductos()
      .then(response => {
        this.productos = response.data;
        console.log('productos:', response.data)
      })
      .catch(error =>{
        console.log(error)
      })
    }

}
</script>
