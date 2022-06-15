<template>
    <ol>
        <div class="mt-2 d-flex justify-content-between align-items-center ps-4" 
        v-for="(tareA, index) in lista_tareas" :key="index">
            <li class="fs-5 mx-2 fw-bold">{{tareA}}</li>
            <button class="btn-dark mx-3 my-1" @click="borrar(index)">Eliminar</button>
        </div>    
    </ol>
</template>

<script>
export default {
    name: 'TareasRender',

    props: {
        lista_tareas: {
            type: Array,
            required: true
        }
    },

    data: function(){
        return {}
    },

    methods: {
        borrar(id) {
            //console.log(`El id es: ${id}`)
            this.$emit('borrar', {id: id})
        } 
    },

    // components: {},
}
</script>

<style scoped>
    div:nth-child(2n) {
        border: 2px solid rgb(255,150,150);
        background: lightgray

    }
        div:nth-child(2n+1) {
        border: 2px solid rgb(150,150,255);
    }
</style>