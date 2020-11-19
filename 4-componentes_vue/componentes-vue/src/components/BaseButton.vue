<template>
  <div 
    v-bind:class="normalizedButtonClass"
    v-on:click="btnOnClick()"
  >
    {{text}}
  </div>
</template>

<script>
export default {
    name: 'BaseButton',
    // Computed es utilizado para operaciones
    // que requieran cierta lógica
    computed: {
        normalizedButtonClass() {
            return `btn btn-${this.type} ${this.extraClass}`;
        },
    },
    // La funcion normalizedButtonClass
    // genera la clase del boton
    // de acuerdo a lo que reciba en los props
    props: {
        text: {
            type: String,
            required: true,
        },
        extraClass: {
            type: String,
            default: '',            
        },
        type: {
            type: String,
            default: 'primary',            
        },
        btnOnClick: {
            type: Function,
            required: true
        },
    },
};
</script>

<style scoped>

    .btn {
        display: inline-block;
        font-weight: 400;
        color: #212529;
        text-align: center;
        vertical-align: middle;
        -webkit-user-select: none;
        -moz-user-select: none;
        -ms-user-select: none;
        user-select: none;
        background-color: transparent;
        border: 1px solid transparent;
        padding: 0.375rem 0.75rem;
        cursor: pointer;
        font-size: 1rem;
        line-height: 1.5;
        border-radius: 0.25rem;
        transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out, border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
    }

    .btn:hover {
        color: #212529;
        text-decoration: none;
    }

    .btn-primary {
        color: #fff;
        background-color: #007bff;
        border-color: #007bff;
    }

    .btn-primary:hover {
        color: #fff;
        background-color: #0069d9;
        border-color: #0062cc;
    }

    .btn-primary:focus, .btn-primary.focus {
        color: #fff;
        background-color: #0069d9;
        border-color: #0062cc;
        box-shadow: 0 0 0 0.2rem rgba(38, 143, 255, 0.5);
    }

    .btn-secondary {
        color: #fff;
        background-color: #6c757d;
        border-color: #6c757d;
    }

    .btn-secondary:hover {
        color: #fff;
        background-color: #5a6268;
        border-color: #545b62;
    }

    .btn-secondary:focus, .btn-secondary.focus {
        color: #fff;
        background-color: #5a6268;
        border-color: #545b62;
        box-shadow: 0 0 0 0.2rem rgba(130, 138, 145, 0.5); 
    }
</style>