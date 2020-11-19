<template>
  <div>
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Conceptos Báscios de Componentes"/>
    <div id="components-demo">
      <ButtonCounter title="Viaje con Vue" />
      <ButtonCounter title="Blog con Vue" />
      <ButtonCounter title="¿Por qué Vue es divertido?" />
    </div>
    <hr>
    <MyComponent 
      v-bind:title="title"
      v-bind:message="message"
      v-bind:primaryCallToAction="primaryButton"
      v-bind:secondaryCallToAction="secondaryButton"
    />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import ButtonCounter from './components/ButtonCounter.vue'
import MyComponent from './components/MyComponent.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    ButtonCounter,
    MyComponent
  },
  data: function() {
        return {
            title: 'Bienvenidos a Vue.js',
            message: 'Vue.js es un framework de JavaScript de código abierto para la construcción de interfaces de usuario y aplicaciones de una sola página.',
            primaryButton: {
              text: 'Leer información',
              btnOnClick: () => {
                alert('Haz hecho clic en el botón primario');
              }
            },
            secondaryButton: {
              text: 'Explorar',
              btnOnClick: () => {
                alert('Haz hecho clic en el botón secundario');
              }
            },
        }
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
