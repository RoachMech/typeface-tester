<template>
    <div class="typeface-loader">
        <select v-model="currentTypeface">
            <option>sans-serif</option>
            <optgroup label="Google Fonts">
                <option>Droid Sans</option>
                <option>Droid Serif</option>
            </optgroup>
            <optgroup label="Typekit">
                <option>omnes-pro</option>
                <option>azo-sans-web</option>
                <option>nimbus-sans</option>
                <option>halyard-display</option>
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