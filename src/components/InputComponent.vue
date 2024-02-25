<template>
    <div class="input">
        <div>{{ formName }}</div>
        <input class="input-inside" :placeholder="formPlaceholder" @change="sendChange" :value="value" type="text" :style="{'background': `url(${image})`, 'background-repeat': 'no-repeat', 'background-position': '90% 50%'}">
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
                image: new URL(`/public/${this.formImageSource}`, import.meta.url),
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
            letter-spacing: 0%;
            line-height: 20px;
        }
        & input {
            color: rgb(111, 108, 144);
            font-size: 18px;
            font-weight: 400;
            letter-spacing: 0%;
            line-height: 20px;            
            text-indent: 20px;
        }
        & :focus {
            border-color: rgb(74, 58, 255);
            border-width: 3px;
        }
    }
    .input-inside {
        background: rgb(255, 255, 255);
        border: 1px solid rgb(239, 240, 247);
        border-radius: 46px;
        box-shadow: 0px 2px 6px 0px rgba(19, 18, 66, 0.07);
        box-sizing: border-box;
        height: 66px;
        width: 284px;
        & :focus {
            border-color: rgb(74, 58, 255);
            border-width: 2px;
        }
    }
    @media (width <= 760px) {
        .input {
            display: flex;
            flex-direction: row;            
            gap: 25px;
            margin-left: -20px;            
            & div {
                min-width: 50px;
            }
            & div {
                font-size: 14px;
            }
            & input {
                font-size: 14px;
                height: 45px;
            }
        }        
        .input-inside {
            box-sizing: border-box;
            margin-top: -10px;
            width: 550px;
        }
    }
</style>