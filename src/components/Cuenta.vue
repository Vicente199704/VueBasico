<template>
  <div class="p-3">
      <h2>Tipo de Cuenta: {{cuenta}}</h2>

           <h2 :class="colorCantidad" v-if="saldo > 500">Saldo: {{saldo}}</h2> <!-- V-if que pintara si el saldo es menor a 500 mediante una etiqueta span-->
           <h2 :class="colorCantidad" v-else-if="saldo <= 500 && saldo >= 0"> Saldo: {{saldo}} </h2>

      <h2 class="text-success p-3" v-if="estado">Cuenta Activa</h2>
      <h2 class="text-danger" v-else>Cuenta Desactivada</h2>

      <div v-for="(servicio,index) in servicios" :key="index"> <!-- Ciclo for para recorrer servicios-->
          {{index + 1 }}-{{ servicio }}
      </div>

        <AccionSaldo 
        class="btn btn-success"
        texto="Aumentar Saldo"
        @accion="aumentar" 
        /> <!--Componente creado en cuenta 
        en texto se utilizan props, en accion se utilizan custom events-->
        <AccionSaldo 
        class="btn btn-danger"
        @accion="disminuir"
        texto="Disminuir Saldo"
        :desactivar = "desactivar"
       
        />
  </div>


</template>

<script>
import AccionSaldo from './AccionSaldo.vue'

export default {
    components:{
        AccionSaldo
    },
    data() {

        return {
            saldo: 1000,
            cuenta: 'Visa',
            estado: true,
            servicios: ['giro','abono','transferencias'],
            desactivar: false
        }

    },
    methods: {
        aumentar(){
            this.saldo = this.saldo+100
            this.desactivar = false

        },
        disminuir(){
            if(this.saldo === 0){
                this.desactivar = true
                alert('Saldo Agotado')
               
            }else{
                 this.saldo = this.saldo-100
            }

        }
   
    },
    computed:{
        colorCantidad(){
            return this.saldo > 500 ? 'text-success' : 'text-danger'
        }
    }
}

</script>

<style>

</style>