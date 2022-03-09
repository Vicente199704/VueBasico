<template>
  <button class="p-2 m-3" @click="accion" :disabled="desactivar"> {{ texto }}  </button> <!-- El boton llamara a la desactivacion cuando sea de tipo false-->
</template>

<script>
export default {

    props:{
        texto: String,
        desactivar: {
            type: Boolean,
            default: false
        }
    },
    methods: {
        accion(){
            this.$emit('accion') //Emit de accion, del componente padre
        }
    }
}

</script>

<style>

</style>