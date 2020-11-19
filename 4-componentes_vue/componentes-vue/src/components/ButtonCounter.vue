<template>
    <div class="blog-post">
        <h3>{{ title }}</h3>
        <button v-on:click="count++">Me ha pulsado {{count}} veces</button>
    </div>
</template>

<script>
export default {
    name: 'ButtonCounter',
    /**Pasando datos a componentes secundarios con Props */
    props: ['title'],
    /** la opción data de un componente debe ser una función */
    data: function() {
        return {
            count: 0,
        }
                
    },
}
</script>

<style scoped>

</style>