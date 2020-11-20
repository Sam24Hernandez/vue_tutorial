<template>
  <div>
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld 
      msg="Componentes en Profundidad" 
      v-bind:likes="42"
      v-bind:is-published="false"
      v-bind:comment-ids="[234, 266, 273]"
      v-bind:author="{ name: 'Sam', company: 'Google Company' }"
      v-bind:date="new Date().toLocaleString()"
      v-bind:func="function Person(fName, lName){this.fName = fName; this.lName = lName;}"
    />
    <PropsType postTitle="Formateando las 'Props'" />
    <hr>
    <h2>Eventos Personalizados</h2>
    <CustomEvent />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import PropsType from "./components/PropsType.vue";
import CustomEvent from "./components/CustomEvent.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    PropsType,
    CustomEvent
  },
};
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
