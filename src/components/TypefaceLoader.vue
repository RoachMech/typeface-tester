<template>
    <div class="typeface-loader">
        <select v-model="currentTypeface">
            <option>sans-serif</option>
            <optgroup label="Typekit">
                <option>omnes-pro</option>
                <option>azo-sans-web</option>
                <option>nimbus-sans</option>
                <option>halyard-display</option>
                <option>niveau-grotesk</option>
                <option>rucksack</option>
                <option>usual</option>
                <option>filson-pro</option>
                <option>canada-type-gibson</option>
                <option>semplicitapro</option>
                <option>effra</option>
                <option>soleil</option>
                <option>europa</option>
                <option>faricy-new-web</option>
                <option>sofia-pro</option>
                <option>interface</option>
                <option>p22-underground</option>
                <option>adrianna</option>
                <option>report</option>
                <option>montserrat</option>
                <option>puritan</option>
                <option>new-cicle</option>
                <option>dulcian-normal</option>
                <option>como</option>
            </optgroup>
        </select>
    </div>
</template>

<script>
    import WebFont from 'webfontloader';

    export default {
        name: "TypefaceLoader",

        data() {
            return {
                currentTypeface: 'sans-serif',
            }
        },

        watch: {
            currentTypeface: {
                immediate: true,
                handler(typeface) {
                    document.documentElement.style.setProperty('--typeface', typeface);
                },
            }
        },

        mounted() {
            WebFont.load({
                google: {
                    families: ['Droid Sans', 'Droid Serif']
                },
                typekit: {
                    id: 'cxc7iyz',
                }
            });
        },
    }
</script>

<style lang="scss">

</style>