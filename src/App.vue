<template>
    <div id="app">
        <typeface-loader/>
        <h1>30 enthousiastelingen die je digitaal vooruit helpen</h1>
        <p>Eerste alinea met tekst</p>
        <h2>Online succes</h2>
        <p>Online succes alinea met tekst</p>
    </div>
</template>

<script>
    import TypefaceLoader from './components/TypefaceLoader';

    export default {
        name: 'app',
        components: {
            'typeface-loader': TypefaceLoader,
        }
    }
</script>

<style lang="scss">
    :root {
        --color: red;
    }

    #app {
        font-family: var(--typeface, sans-serif);
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        color: #000;
        margin-top: 60px;
    }
</style>
