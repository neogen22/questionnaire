<template>
    <button :class="buttonCSSType" @click="this.$root.dynamicComponent = this.nameOfComponentTo" :disabled="disabled">{{buttonText}}</button>
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
            },
            disabled : {
                type: Boolean,
                requierd: true
            }
        },
    }
</script>

<style scoped>
    .button-next {
        align-items: center;
        align-self: flex-end;
        background-color: rgb(74, 58, 255);
        border: none;
        border-radius: 56px;
        box-sizing: border-box;
        color: white;
        cursor: pointer;
        display: flex;
        font-family: 'DM Sans';        
        font-size: 18px;
        height: 61px;
        justify-content: center;
        margin-top: 32px;
        transition: all 200ms;
        width: 171px;
        -webkit-tap-highlight-color: rgba(0, 0, 0, 0)
    } 
    .button-next:active {
        color:rgb(74, 58, 255);
    }
    .button-previous {
        align-items: center;
        background-color: white;
        border: 1px solid rgb(74, 58, 255);
		border-radius: 66px;
        box-sizing: border-box;
        color: rgb(74, 58, 255);
        display: flex;
        cursor: pointer;
        font-family: 'DM Sans';
        font-size: 18px;
        font-weight: 400;        
        height: 61px;
        justify-content: center;        
        line-height: 20px;
        margin-top: 32px;
        transition: all 200ms;           
        width: 192px;
        -webkit-tap-highlight-color: rgba(0, 0, 0, 0)
    }
    .button-previous:active {
        color: white;
    }
    @media (width <= 760px) {
        .button-next {
            align-items: center;
            align-self: flex-end;
            background-color: rgb(74, 58, 255);
            border: none;            
            border-radius: 56px;
            box-sizing: border-box;
            color: white;   
            cursor: pointer;
            display: flex;
            font-family: 'DM Sans';
            font-size: 14px;
            height: 46px;            
            justify-content: center;            
            margin-top: 16px;
            width: 120px;
            -webkit-tap-highlight-color: rgba(0, 0, 0, 0)
        }
        .button-previous {
            align-items: center;
            background-color: white;
            border: 1px solid rgb(74, 58, 255);
            border-radius: 66px;
            box-sizing: border-box;
            color: rgb(74, 58, 255);
            cursor: pointer;
            display: flex;
            font-size: 14px;
            font-weight: 400;            
            height: 46px;
            line-height: 20px;            
            justify-content: center;
            margin-top: 16px;
            width: 120px;
            -webkit-tap-highlight-color: rgba(0, 0, 0, 0)
        }
    }
</style>
