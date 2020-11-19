<template>
  <div>
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Bienvenidos a las Funciones de Vuejs" />
    <div v-if="Math.random() > 0.5">
      Ahora me ves
    </div>
    <div v-else>
      Ahora no me ves
    </div>
    <hr>
    <h2>Mapeando una matriz a elementos con v-for</h2>
    <!-- #Ejemplo 1
      También puede usar of como delimitador en lugar de in, de modo que esté más cerca 
      de la sintaxis de JavaScript para los iteradores:
      v-for="item of items"
      <ul id="example-1">
      <li v-for="item in items" :key="item.messages">
        {{item.message}}
      </li>    
    </ul>
    -->
    <ul id="example-2">
      <li v-for="(item, index) in items" :key="item.messages">
        {{firstMessage}} - {{index}} - {{item.message}}
      </li>    
    </ul>

  <h3>v-for con un Objeto</h3>
    <ul id="v-for-object" class="demo">
      <li v-for="(value, key, index) in object" :key="value">
        {{index}}. {{key}}: {{value}}
      </li>
    </ul>

    <h3>Mostrando Resultados Filtrados/Ordenados</h3>
    <li v-for="n in numerosImpares" :key="n">{{n}}</li>

    <div>
      <h4>v-for con un Rango</h4>
      <span v-for="n in 10" :key="n">{{ n }}</span>
    </div>
    <hr>
    <h2>Manejo de eventos</h2>
    <button v-on:click="counter += 1">Añadir 1</button>
    <p>Se ha hecho clic en el botón de arriba {{counter}} veces.</p>
    <h3>Métodos Manejadores de Eventos</h3>
    <button v-on:click="saludar">Saludar</button>
    <h3>Métodos Manejadores en línea</h3>
    <button v-on:click="di('hola')">Di hola</button>
    <button v-on:click="di('que')">Di que</button>
    <h3>Modificadores de eventos</h3>
    <!-- Se detendrá la propagación del evento click. -->
    <a v-on:click.stop="hasEsto"></a>
    
    <!-- El evento de enviar ya no volverá a cargar la página. -->
    <form v-on:submit.prevent="onSubmit"></form>
    
    <!-- Los modificadores pueden encadenarse -->
    <a v-on:click.stop.prevent="hasEsto"></a>
    
    <!-- solo el modificador -->
    <form v-on:submit.prevent></form>
    
    <!-- utilizar el modo de captura al agregar el detector de eventos -->
    <!-- es decir, un evento dirigido a un elemento interno se maneja aquí antes de ser manejado por ese elemento -->
    <div v-on:click.capture="hazEsto">...</div>
    
    <!-- solo activa el controlador si event.target es el elemento en sí -->
    <!-- es decir, no de un elemento hijo -->
    <div v-on:click.self="hazEso">...</div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data: () => ({
    firstMessage: 'Mensaje',
    items: [
      { message: 'Sam' },
      { message: 'Ivana' },
      { message: 'Juntos' }
    ],
    object: {
      firstName: 'Sam',
      lastName: 'Hernandez',
      age: 19
    },
    numeros: [ 1, 2, 3, 4, 5 ],
    /**Contador / Escuchar eventos */
    counter: 0,
    name: 'Vue.js'
  }),
  computed: {
    numerosImpares: function() {
      return this.numeros.filter(function(numero){
        return numero % 2 === 0
      })
    }
  },
  methods: {
    saludar: function(e) {
      // `this` dentro de los métodos apunta a la instancia de Vue
      alert('Hola ' + this.name + '!');
      // `e` es el evento DOM nativo
      if(e) {
        alert(e.target.tagName);
      }
    },
    di: function(message) {
      alert(message)
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

ul {
  margin: 0;
  padding: 0;
  list-style-type: circle;
}
</style>
