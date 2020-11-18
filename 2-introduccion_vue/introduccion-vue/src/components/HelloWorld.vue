<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <!-- Propiedades computadas -->
    <!--<p>{{message.split('').reverse().join('')}}</p>-->
    <p>Mensaje original: "{{ message }}"</p>
    <p>Mensaje invertido computado: "{{ reversedMessage }}"</p>
    <p>Mi nombre es {{fullName}}</p>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: {
      type: String,
      required: false 
    },    
  },
   data: () => ({
    message: "Hola Mundo",
    firstName: "Sam",
    lastName: "Hernández"
  }),
  computed: {
    reversedMessage: function() {
      return this.message.split('').reverse().join('');
    },
    fullName: function() {
      return this.firstName + ' ' + this.lastName;
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
</style>
