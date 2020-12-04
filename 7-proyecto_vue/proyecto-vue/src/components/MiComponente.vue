<template>
    <div id="mi-componente">
        <h1>Este es Mi Componente</h1>
        <h2>{{subtitle}}</h2>
    </div>
</template>

<script>
export default {
  name: 'MiComponente',
  data() {
      return {
          subtitle: 'Sou el subtitulo de mi componente'
      }
  }
}
</script>