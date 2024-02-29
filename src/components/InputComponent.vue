<template>
    <div class="input" >
        <div :class="{'err': disabled}">{{ formName }}</div>
        <input class="input-inside" :placeholder="formPlaceholder" @input="$emit('update:modelValue', $event.target.value)" :value="modelValue" type="text" :style="{'background': `url(${formImageSource})`, 'background-repeat': 'no-repeat', 'background-position': '90% 50%'}">
    </div>
</template>
<script>
    export default {
        props: {
            formImageSource: {
                type: String,
                required: true
            },
            formName: {
                type: String,
                required: true
            },
            formPlaceholder: {
                type: String,
                required: true
            },
            disabled: {
                type: Boolean,
                required: false,
            },
            modelValue: {
                type: String,
                required: true
            },
        },
        data() {
            return {
                image: new URL(`/public/${this.formImageSource}`, import.meta.url),
            }
        },
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
            font-family: 'DM Sans';
            font-size: 18px;
            font-weight: 500;
            letter-spacing: 0%;
            line-height: 20px;
        }
        & input {
            color: rgb(111, 108, 144);
            font-family: 'DM Sans';
            font-size: 18px;
            font-weight: 400;
            letter-spacing: 0%;
            line-height: 20px;            
            text-indent: 20px;
        }
        & :focus {
            border-width: 1px;
            border-color: rgb(74, 58, 255);
            box-shadow: none;
            outline-color: rgb(74, 58, 255);
            outline-style:solid;
            outline-width: 3px;
        }
        & .err {
            color: red
        }
    }
    .input-inside {
        background: rgb(255, 255, 255);
        outline: 1px solid rgb(239, 240, 247);
        border-radius: 46px;
        box-shadow: 0px 2px 6px 0px rgba(19, 18, 66, 0.07);
        box-sizing: border-box;
        height: 66px;
        width: 284px;
        & :focus {
            border-width: 1px;
            border-color: rgb(74, 58, 255);
            box-shadow: none;
            outline-color: rgb(74, 58, 255);
            outline-style:solid;
            outline-width: 3px;
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
                font-family: 'DM Sans';
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