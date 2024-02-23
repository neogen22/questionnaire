<template>
    <div class="input">
        <img :src="formImageSource">
        <div>{{ formName }}</div>
        <input class="input-inside" :placeholder="formPlaceholder" @change="sendChange" :value="value" type="text">
    </div>
</template>
<script>
    export default {
        props: {
            formImageSource: String,
            formName: String,
            formPlaceholder: String,
            value: String
        },
        data() {
            return {
                image: new URL(`/public/${this.formImageSource}`, import.meta.url).href,
            }
        },
        methods: {
            sendChange(event) {
                this.$emit('customChange', event.target.value)
            }
        }
    }
</script>
<style scoped>
    input {
        all: unset;
    }
    .input {
        display: flex;
        flex-direction: column;
        gap: 18px;
        & div {
            color: rgb(23, 15, 73);
            font-size: 18px;
            font-weight: 500;
            line-height: 20px;
            letter-spacing: 0%;
                }
        & input {
            text-indent: 20px;
            color: rgb(111, 108, 144);
            font-size: 18px;
            font-weight: 400;
            line-height: 20px;
            letter-spacing: 0%;
        }
        & img {
            width: 30px;
            height: 30px;                    
            position: absolute; 
            margin-left: 240px; 
            margin-top: 55px;
        }
        & :focus {
            border-color: rgb(74, 58, 255);
            border-width: 3px;
        }
    }
    .input-inside {
        width: 284px;
        height: 66px;
        box-sizing: border-box;
        border: 1px solid rgb(239, 240, 247);
        border-radius: 46px;
        box-shadow: 0px 2px 6px 0px rgba(19, 18, 66, 0.07);
        background: rgb(255, 255, 255);
        & :focus {
            border-color: rgb(74, 58, 255);
            border-width: 2px;
        }
    }
</style>