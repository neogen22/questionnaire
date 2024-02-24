<template>    
    <component :is="dynamicComponent"/>
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
</style>
