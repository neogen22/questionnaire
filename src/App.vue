<template>
    <body>
        <component :is="dynamicComponent"/>
    </body>
</template>

<script>
import FormFirst from './components/FormFirst.vue';
import FormSecond from './components/FormSecond.vue';
import FormThird from './components/FormThird.vue'
import FormFourth from './components/FormFourth.vue'
export default {
    components: {
        FormFirst,
        FormSecond,
        FormThird,
        FormFourth
    },
    provide: {
        superObject: {},
    },
    data() {
        return {
            dynamicComponent: 'FormFirst'
        }
    },
}
</script>

<style scoped>
    body {
        display: grid;
        padding: 2rem 2rem;
        place-items: center;
    }
    @media (width <= 760px) {
        body {
            margin-left: -25px;
        }
    }
</style>
