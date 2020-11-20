<template>
    <li class="d-flex align-items-center list-group-item">        
        <button 
            class="btn border-0 flex-grow-1 text-left shadow-sm"
            :class="{completed}"
            @click="$emit('on-toggle')"
            v-if="!isEditing"
        >
            <span>{{description}}</span>
        </button>
        <form v-else class="flex-grow-1" @submit.prevent="finishEditing()">
            <input 
                class="form-control"
                type="text"
                v-model="newTodoDescription"
                @blur="finishEditing"
                ref="newTodo"
            >
        </form>
        <button
            @click="startEditing"
            class="btn btn-outline-primary border-0"
        >
            <span class="fa fa-edit">Editar</span>
        </button>
        <button
            @click="$emit('on-remove')"
            class="btn btn-outline-danger border-0"
        >
            <span class="fa fa-trash">Eliminar</span>
        </button>
    </li>
</template>

<script>
export default {
    name: 'TodoListItem',
    props: {
        description: String,
        completed: Boolean
    },
    data: function() {
        return {
            isEditing: false,
            newTodoDescription: ''
        };
    },
    methods: {
        startEditing() {
            if(this.isEditing) {
                this.finishEditing();
            } else {
                this.newTodoDescription = this.description;
                this.isEditing = true;
                this.$nextTick(() => this.$refs.newTodo.focus());
            }
        },
        finishEditing() {
            this.isEditing = false;
            this.$emit("on-edit", this.newTodoDescription);
        }
    }
};
</script>

<style scoped>
    .completed {
        text-decoration: line-through;
    }

    .border-0 {
        border: 0 !important;
    }

    .d-flex {
        display: -ms-flexbox !important;
        display: flex !important;
    }

    .flex-grow-1 {
        -ms-flex-positive: 1 !important;
        flex-grow: 1 !important;
    }

    .align-items-center {
        -ms-flex-align: center !important;
        align-items: center !important;
    }

    .text-left {
        text-align: left !important;
    }

    .shadow-sm {
        box-shadow: 0 0.125rem 0.25rem rgba(0, 0, 0, 0.075) !important;
    }

    .list-group-item {
        position: relative;
        display: block;
        padding: 0.75rem 1.25rem;
        background-color: #fff;
        border: 1px solid rgba(0, 0, 0, 0.125);
    }

    .list-group-item:first-child {
        border-top-left-radius: inherit;
        border-top-right-radius: inherit;
    }

    .list-group-item:last-child {
        border-bottom-right-radius: inherit;
        border-bottom-left-radius: inherit;
    }   
    
    .list-group-item.disabled, .list-group-item:disabled {
        color: #6c757d;
        pointer-events: none;
        background-color: #fff;
    }

    .list-group-item.active {
        z-index: 2;
        color: #fff;
        background-color: #007bff;
        border-color: #007bff;
    }

    .list-group-item + .list-group-item {
        border-top-width: 0;
    }

    .list-group-item + .list-group-item.active {
        margin-top: -1px;
        border-top-width: 1px;
    }

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
        font-size: 1rem;
        line-height: 1.5;
        border-radius: 0.25rem;
        transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out, border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
    }

    @media (prefers-reduced-motion: reduce) {
        .btn {
            transition: none;
        }
    }

    .btn:hover {
        color: #212529;
        text-decoration: none;
        background-color: #f3f3f3;
    }

    .btn:focus, .btn.focus {
        outline: 0;
        box-shadow: 0 0 0 0.2rem rgba(0, 123, 255, 0.25);
    }

    .btn.disabled, .btn:disabled {
        opacity: 0.65;
    }

    .btn:not(:disabled):not(.disabled) {
        cursor: pointer;
    }

    .btn-outline-primary {
        color: #007bff;
        border-color: #007bff;
    }

    .btn-outline-primary:hover {
        color: #fff;
        background-color: #007bff;
        border-color: #007bff;
    }

    .btn-outline-primary:focus, .btn-outline-primary.focus {
        box-shadow: 0 0 0 0.2rem rgba(0, 123, 255, 0.5);
    }

    .btn-outline-danger {
        color: #dc3545;
        border-color: #dc3545;
    }

    .btn-outline-danger:hover {
        color: #fff;
        background-color: #dc3545;
        border-color: #dc3545;
    }

    .btn-outline-danger:focus, .btn-outline-danger.focus {
        box-shadow: 0 0 0 0.2rem rgba(220, 53, 69, 0.5);
    }

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