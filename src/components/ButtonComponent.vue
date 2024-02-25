<template>
    <button :class="buttonCSSType" @click="this.$root.dynamicComponent = this.nameOfComponentTo">{{buttonText}}</button>
</template>

<script>
    export default {
        props: {
            nameOfComponentTo: {
                type: String,
                requierd: true
            },
            buttonText: {
                type: String,
                requierd: true
            },
            buttonCSSType: {
                type: String,
                required: true
            }
        },
    }
</script>

<style scoped>
    .button-next {
        width: 171px;
        height: 61px;
        background-color: rgb(74, 58, 255);
        border-radius: 56px;
        color: white;        
        font-size: 18px;
        display: flex;
        align-items: center;
        justify-content: center;
        box-sizing: border-box;
        margin-top: 32px;
        align-self: flex-end;
        border: none;
        transition: all 200ms;
    } 
    .button-next:active {
        color:rgb(74, 58, 255);
    }
    .button-previous {
        width: 192px;
        height: 61px;
        font-size: 18px;
        display: flex;
        align-items: center;
        justify-content: center;
        box-sizing: border-box;
        border: 1px solid rgb(74, 58, 255);
		border-radius: 66px;
        margin-top: 32px;
        color: rgb(74, 58, 255);
        font-weight: 400;
        line-height: 20px;
        background-color: white;
        transition: all 200ms;
    }
    .button-previous:active {
        color: white;
    }
    @media (width <= 760px) {
        .button-next {
            width: 120px;
            height: 46px;
            background-color: rgb(74, 58, 255);
            border-radius: 56px;
            color: white;        
            font-size: 14px;
            display: flex;
            align-items: center;
            justify-content: center;
            box-sizing: border-box;
            margin-top: 16px;
            align-self: flex-end;
            border: none;
        }
        .button-previous {
            width: 120px;
            height: 46px;
            font-size: 14px;
            display: flex;
            align-items: center;
            justify-content: center;
            box-sizing: border-box;
            border: 1px solid rgb(74, 58, 255);
            border-radius: 66px;
            margin-top: 16px;
            color: rgb(74, 58, 255);
            font-weight: 400;
            line-height: 20px;
            background-color: white;
        }
    }
</style>
