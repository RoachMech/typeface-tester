<template>
    <div class="typeface-loader">
        <button type="button" @click="previousTypeface"> &laquo; </button>
        <select v-model="currentTypeface" class="typeface-loader__select">
            <option v-for="typeface in typefaces" v-bind:key="typeface">
                {{ typeface }}
            </option>
        </select>
        <button type="button" @click="nextTypeface"> &raquo; </button>
    </div>
</template>

<script>
    import WebFont from 'webfontloader';

    export default {
        name: "TypefaceLoader",

        data() {
            return {
                currentTypeface: 'sans-serif',
                typefaces: [
                    'sans-serif',
                    'omnes-pro',
                    'azo-sans-web',
                    'nimbus-sans',
                    'halyard-display',
                    'niveau-grotesk',
                    'rucksack',
                    'usual',
                    'filson-pro',
                    'canada-type-gibson',
                    'semplicitapro',
                    'effra',
                    'soleil',
                    'europa',
                    'faricy-new-web',
                    'sofia-pro',
                    'interface',
                    'p22-underground',
                    'adrianna',
                    'report',
                    'montserrat',
                    // 'puritan',
                    // 'new-cicle',
                    // 'dulcian-normal',
                    'como',
                    'quiet-sans',
                    'graphie',
                    'work-sans',
                    'poppins',
                    'cresta',
                    'quasimoda',
                    'questa-sans',
                    'circe',
                    'Source Sans Pro'
                ],
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
                    families: ['Source Sans Pro:400,900']
                },
                typekit: {
                    id: 'cxc7iyz',
                }
            });

            window.addEventListener('keyup', (e) => {
                if (e.key === 'ArrowLeft') {
                    this.previousTypeface();
                }
                if (e.key === 'ArrowRight') {
                    this.nextTypeface();
                }
            });
        },

        methods: {
            nextTypeface() {
                const index = this.typefaces.indexOf(this.currentTypeface);

                if (index >= 0 && index < this.typefaces.length - 1) {
                    this.currentTypeface = this.typefaces[index + 1];
                }
            },

            previousTypeface() {
                const index = this.typefaces.indexOf(this.currentTypeface);

                if (index >= 1) {
                    this.currentTypeface = this.typefaces[index - 1];
                }
            }
        }
    }
</script>

<style lang="scss">
    .typeface-loader {
        align-items: center;
        display: flex;
        justify-content: space-between;
        width: 100%;
    }
    .typeface-loader__select {
        font-size: 16px;
    }
</style>