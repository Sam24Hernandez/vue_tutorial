<template>
  <div class="custom-event">
      <my-button @click="handleClick">
          Botón de ejemplo
      </my-button>
      <button type="submit"><slot>Enviar</slot></button>
  </div>
</template>

<script>
import MyButton from './MyButton.vue';

export default {
  components: { MyButton },
    name: 'CustomEvent',
    methods: {
        handleClick(info) {
            console.log('Evento clic en el botón: ' + info);
        }
    }    
}
</script>

<style scoped>

</style>