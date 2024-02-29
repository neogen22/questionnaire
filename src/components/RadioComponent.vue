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
            value: {
                type: String,
                required: true
            },
            active: {
                type: Boolean,
                required: true
            },
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
        color: rgb(23, 15, 73);
        font-family: 'DM Sans';
        font-size: 16px;
        font-weight: 400;
        line-height: 17px;
        letter-spacing: 2%;
        margin-left: 5px;
    }
    input[type='radio'] {
        border-radius: 50%;
        height: 17px;
        width: 17px;
    }
    div {
        align-items: center;
        background: rgb(255, 255, 255);
        border: 1px solid rgb(239, 240, 247);
		border-radius: 16px;
        box-shadow: 0 2px 6px 0 rgba(19, 18, 66, 0.07);
        box-sizing: border-box;
        display: flex;
        height: 115px;
        padding-left: 26px;
        & div {
            color: rgb(23, 15, 73);
            font-size: 16px;
            font-weight: 400;            
            letter-spacing: 2%;
            line-height: 17px;
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
