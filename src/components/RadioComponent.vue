<template>
    <div @click="action">
        <input type="radio" value="value" :id="value" :checked="active" @click="action">
        <label :for="value">{{ value }}</label>
    </div>
</template>
<script>
    export default {
        inject: ['superObject'],
        props: {
            value: String,
            active: Boolean,
        },
        methods: {
            action() {
                this.$emit('activate-radio-button', this.value)
            }
        },
    }
</script>
<style scoped>
    label {
        margin-left: 5px;
        color: rgb(23, 15, 73);
        font-size: 16px;
        font-weight: 400;
        line-height: 17px;
        letter-spacing: 2%;
    }
    input[type='radio'] {
        border-radius: 50%;
        width: 17px;
        height: 17px;
    }
    div {
        padding-left: 26px;
        box-sizing: border-box;
        border: 1px solid rgb(239, 240, 247);
		border-radius: 16px;
        box-shadow: 0 2px 6px 0 rgba(19, 18, 66, 0.07);
        background: rgb(255, 255, 255);
        height: 115px;
        display: flex;
        align-items: center;            
        & div {
            color: rgb(23, 15, 73);
            font-size: 16px;
            font-weight: 400;
            line-height: 17px;
            letter-spacing: 2%;
            padding-left: 5px;
        }
    }
    @media (width <= 760px) {
        div {
            height: 45px;
            margin-left: -25px;
        }
    }
</style>
