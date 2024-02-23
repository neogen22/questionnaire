<template>
    <body>        
        <FormFirst @changeslide="count = $event" v-if="count === 0"/>
        <FormSecond @changeslide="count = $event" @changeslideback="count = $event" v-if="count === 1"/>
        <FormThird @changeslide="count = $event" @changeslideback="count = $event" v-if="count === 2"/>
        <FormFourth @changeslideback="count = $event" v-if="count === 3"/>
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
        superObject: {}
    },
    data() {
        return {
            count: 0,
        }
    },
}

</script>

<style scoped>
</style>
