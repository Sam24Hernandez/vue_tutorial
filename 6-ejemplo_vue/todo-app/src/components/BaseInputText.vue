<template>
    <form class="col-12 col-sm-10 col-md-8 cl-lg-6" @submit.prevent="addTodo()">
      <input 
        v-model="newTodo"
        type="text"
        class="form-control"
        placeholder="Añadir una nueva tarea..."
      >
    </form>   
</template>

<script>
export default {
  data: function() {
    return {
      newTodo: ''
    };
  },
  methods: {
    addTodo() {
      if(this.newTodo.length > 0) {
        this.$emit("on-new-todo", this.newTodo);
      }
      this.newTodo = '';
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .form-control {
    display: block;
    width: 100%;
    height: calc(1.5em + 0.75rem + 2px);
    padding: 0.375rem 0.75rem;
    font-size: 1rem;
    font-weight: 400;
    line-height: 1.5;
    color: #495057;
    background-color: #fff;
    background-clip: padding-box;
    border: 1px solid #ced4da;
    border-radius: 0.25rem;
    transition: border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
  }

  @media (prefers-reduced-motion: reduce) {
    .form-control {
      transition: none;
    }
  }

  .form-control::-ms-expand {
    background-color: transparent;
    border: 0;
  }

  .form-control:-moz-focusring {
    color: transparent;
    text-shadow: 0 0 0 #495057;
  }

  .form-control:focus {
    color: #495057;
    background-color: #fff;
    border-color: #80bdff;
    outline: 0;
    box-shadow: 0 0 0 0.2rem rgba(0, 123, 255, 0.25);
  }

  .form-control::-webkit-input-placeholder {
    color: #6c757d;
    opacity: 1;
  }

  .form-control::-moz-placeholder {
    color: #6c757d;
    opacity: 1;
  }

  .form-control:-ms-input-placeholder {
    color: #6c757d;
    opacity: 1;
  }

  .form-control::-ms-input-placeholder {
    color: #6c757d;
    opacity: 1;
  }

  .form-control::placeholder {
    color: #6c757d;
    opacity: 1;
  }

  .form-control:disabled, .form-control[readonly] {
    background-color: #e9ecef;
    opacity: 1;
  }
</style>
