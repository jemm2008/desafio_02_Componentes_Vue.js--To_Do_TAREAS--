<template>
    <div>
        <h1 class="fw-bold">{{title}}</h1>
        <div class="d-flex justify-content-center mt-3">
            <h4 class="fw-bold text-primary m-0 me-3">{{subtitle01}}</h4>
            <input type="text" ref="tarea" v-model="tarea_ingresada" @keyup.enter="addToDo">
            <button class="ms-3 px-2 btn-success" @click="addToDo">Crear</button>
        </div>
        <div class="d-flex flex-column align-items-center mt-5">
            <h3 class="mt-4 mb-2 ms-4 text-danger fw-bold">{{subtitle02}}</h3>
            <!-- Al hijo: "TareasRender", 
            su padre: "FormulaRio" le envía el array: "lista_tareas" como "prop",
            para que renderice la lista de tareas que contiene. -->
            <TareasRender 
            :lista_tareas="lista_tareas"
            @borrar="borrar_tarea"
            />
        </div>
    </div>
</template>

<script>
    import TareasRender from '@/components/TareasRender.vue'

    export default {
        name: 'FormulaRio',
        // props: {},
        data: function(){
            return {
                title: "Crear una nueva Tarea",
                subtitle01: "Tarea: ",
                subtitle02: "Lista de Actividades por realizar:",
                tarea_ingresada: "",
                lista_tareas: []
            }
        },
        methods: {
                addToDo() {
                    this.lista_tareas.push(this.tarea_ingresada)
                    //console.log(this.lista_tareas)
                    this.tarea_ingresada = ""
                    this.$refs.tarea.focus()
                },
                borrar_tarea(event){
                    // console.log(`el evento escuchado es: ${event.id}`)
                    // console.log(this.lista_tareas)
                    // console.log(this.lista_tareas[event.id])
                    this.lista_tareas.splice(event.id, 1)
                    //console.log(this.lista_tareas)
                }
        },
        components: {
            TareasRender
        },
    }
</script>

<style scoped>
</style>