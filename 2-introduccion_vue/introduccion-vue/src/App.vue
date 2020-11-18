<template>
  <div class="home">
    <img alt="Vue Logo" src="./assets/logo.png" />
    <HelloWorld msg="Bienvenidos a la Introducción a Vue.js" />
    <button @click="increment()">Incrementar:</button>
    <br>
    <span><strong>Valor</strong>: {{value}}</span>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
  },
  data: () => ({
    value: 20
  }),
  methods: {
    increment() {
      this.value++;
    }
  }
};
</script>

<style lang="scss">

body {
  background-color: #2c3e50;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
}

span {
  line-height: 5;
}

button {
  background: #2577fd;
  -moz-user-select: none;
  text-transform: capitalize;
  color: #fff;
  cursor: pointer;
  display: inline-block;
  font-size: 18px;
  font-weight: 400;
  letter-spacing: 1px;
  line-height: 0;
  margin-bottom: 0;
  padding: 27px 44px;
  border-radius: 25px;
  margin: 10px;
  cursor: pointer;
  transition: color 0.4s linear;
  position: relative;
  z-index: 1;
  border: 0;
  overflow: hidden;
  margin: 0;

  &::before {
  content: "";
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background: #00b1ff;
  z-index: 1;
  border-radius: 5px;
  transition: transform 0.5s;
  transition-timing-function: ease;
  transform-origin: 0 0;
  transition-timing-function: cubic-bezier(0.5, 1.6, 0.4, 0.7);
  transform: scaleX(0);
  }

  &:hover::before {
  transform: scaleX(1);
  color: #fff !important;
  z-index: -1;
  }
}
</style>
