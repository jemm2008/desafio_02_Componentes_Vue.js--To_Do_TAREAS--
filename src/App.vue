<template>
    <div class="container">
        <FormulaRio/>
    </div>
</template>

<script>
    import FormulaRio from '@/components/FormulaRio.vue'

    export default {
        name: 'App',
        components: {
            FormulaRio
        }
    }
</script>

<style>
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 80px;
    }
    body {
        background: url('@/assets/to_do_bg.jpg');
    }
</style>
