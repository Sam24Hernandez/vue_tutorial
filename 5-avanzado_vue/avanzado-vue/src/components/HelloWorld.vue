<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <span>Se publicó: {{isPublished}}</span><br>
    <small>{{author}} | {{date}}</small><br>
    <button>Likes: {{likes}}</button>
    <h3>Comentarios {{commentIds}}</h3>  <br>
    <p>{{func}}</p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    /**Tipos de propiedades */
    msg: String, // Cadena de texto
    likes: Number, // Número
    isPublished: Boolean, // Booleano
    commentIds: Array, // Arreglo
    author: Object, // Objeto
    date: Date, // Fecha
    func: Function, // Función
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
