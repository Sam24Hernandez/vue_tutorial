<template>
  <div class="props">
      <h2>Validación de Propiedades</h2>
      <p>Propiedades</p>
      <ul>
          <li>{{propD}}</li>
          <li>{{propE}}</li>
      </ul>
  </div>
</template>

<script>
export default {
    name: 'PropsType',
    props: {
        // Comprobación de tipo básico (`null` coincide con cualquier tipo)
        propA: Number,
        // Múltiples tipos posibles
        propB: [String, Number],
        // Cadena de texto obligatoria
        propC: {
            type: String,
            required: true
        },
        // Número con un valor por defecto
        propD: {
            type: Number,
            default: 100
        },
        // Objeto con un valor por defecto
        propE: {
            type: Object,
            // Los valores predeterminados del objeto o matriz deben devolverse desde
            // una función de fábrica
            default: function() {
                return { message: 'Hola, ¿como estás?' }
            }
        },
        // Función de validación personalizada
        propF: {
            validator: function(value) {
                // El valor debe coincidir con una de estas cadenas de texto
                return [ 'success', 'warning', 'danger' ].indexOf(value) !== -1
            }
        }
    }
}
</script>

<style scoped>

</style>