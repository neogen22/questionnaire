<template>
    <div class="container-for-form-full">
        <span>Get a project quote</span>
        <span>Please fill the form below to receive a quote for your project. Feel free to add as much detail as needed.</span>
        <div class="container-for-form">
            <div class="container-for-form-numbers">
                <div><div>1</div></div>
                <div><div></div></div>
                <div>2</div>
                <div><div></div></div>
                <div>3</div>
                <div></div>
                <div>4</div>
            </div>
            <hr>
            <div class="container-for-form-header">Our services</div>
            <div class="container-for-form-description">Please select which service you are interested in.</div>
            <div class="form">
                <div class="form-container-page-2">
                    <CheckBoxComponent name="Development" checkBoxImageSource="public\developmentIcon.svg"/>
                    <CheckBoxComponent name="Web Design" checkBoxImageSource="public\WebDesignIcon.svg" />
                    <CheckBoxComponent name="Marketing" checkBoxImageSource="public\marketing.svg" />
                    <CheckBoxComponent name="Other" checkBoxImageSource="public\other.svg" />
                </div>
            </div>
        </div>
        <div class="buttons-next-and-previous-flex">
            <button class="button-previous" @click="changeSlideBack()">Previous step</button>
            <button class="button-next" @click="changeSlide()">Next step</button>
        </div>
    </div>
</template>
<script>
    import CheckBoxComponent from './CheckBoxComponent.vue'
    export default {
        inject: ['superObject'],
        components: {
            CheckBoxComponent,
        },
        methods: {
            changeSlide() {
                this.$emit('changeslide', 2)                
            },
            changeSlideBack() {
                this.$emit('changeslideback', 0)
            }
        }
    }    
</script>
<style scoped>
    .buttons-next-and-previous-flex {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        & .button-previous {
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
        }
        & .button-next {
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
            border: none;
        }
    }
    .form-container-page-2 {
        display: grid;
        grid-template-columns: 284px 284px;
        column-gap: 28px;
        row-gap: 21px;
        & > div {
            padding-left: 26px;
            box-sizing: border-box;
            border: 1px solid rgb(239, 240, 247);
			border-radius: 16px;
            box-shadow: 0 2px 6px 0 rgba(19, 18, 66, 0.07);
            background: rgb(255, 255, 255);
            height: 115px;
            display: flex;
            align-items: center;
            transition-property: border-color;
            transition-duration: 0.5s;
            & img {
                width: 66px;
            }
            & div {
                color: rgb(23, 15, 73);
                font-size: 18px;
                font-weight: 500;
                line-height: 20px;
                padding-left: 12px;
            }
        }
        & .active {
            border: 2px solid rgb(74, 58, 255);
        }
    }
    .container-for-form-full {
        display: flex;
        flex-direction: column;
        margin-left: 60px;
        & .container-for-form {
            width: 698px;
            min-height: 606px;
            border-radius: 48px;
            box-shadow: 0 6px 54px 0 rgba(20, 20, 43, 0.07);
            background: rgb(255, 255, 255);
            padding-bottom: 86px;
        }
        & .form {
            display: grid;
            grid-template-columns: 284px 284px;
            margin-left: 46px;
            column-gap: 28px;
            row-gap: 44px;
        }
        & .container-for-form-numbers {
            box-sizing: border-box;
            column-gap: 18px;
            display: flex;        
            height: 34px;
            padding-top: 34px;
            padding-left: 89px;
            padding-bottom: 58px;
            & div:first-child, div:nth-child(3) {
                display: flex;
                color: rgb(255, 255, 255);
                font-size: 16px;
                font-weight: 500;
                line-height: 18px;
                background: rgb(74, 58, 255);
                width: 34px;
                height: 34px;
                border-radius: 50%;
                justify-content: center;
                align-items: center;
            }
            & div:nth-child(2), div:nth-child(4), div:nth-child(6) {
                width: 98px;
                height: 6px;
                border-radius: 40px;
                background: rgb(239, 240, 247);
                margin-top: 12px;
            }
            & div:nth-child(2) div {
                width: 98px;
                height: 6px;
                border-radius: 40px;
                background: rgb(74, 58, 255);
            }
            div:nth-child(4) div {
                width: 49px;
                height: 6px;
                border-radius: 40px;
                background: rgb(74, 58, 255);
            }
            & div:nth-child(5), div:nth-child(7) {
                display: flex;
                color: rgb(111, 108, 144);
                font-size: 16px;
                font-weight: 500;
                line-height: 18px;
                background: rgb(239, 240, 247);
                width: 34px;
                height: 34px;
                border-radius: 50%;
                justify-content: center;
                align-items: center;
            }        
        }
        & span:first-child {
            display: block;
            color: rgb(23, 15, 73);
            font-size: 34px;
            font-weight: 700;
            line-height: 46px;
            text-align: center;
            width: 680px;            
            margin-bottom: 12px;
        }
        & span:nth-child(2) {
            display:block;
            color: rgb(111, 108, 144);
            font-size: 18px;
            font-weight: 400;
            line-height: 30px;
            text-align: center;
            width: 517px;
            margin-left: 82px;
            margin-bottom: 42px;
        }
        & hr {
            width: 596px;
            border: 1px solid rgb(217, 219, 233);
            margin-bottom: 64px;
            margin-left: 50px;
        }
        & .container-for-form-header {
            color: rgb(23, 15, 73);
            font-size: 24px;
            font-weight: 700;
            line-height: 35px;
            padding-left: 46px;
            height: 35px;
            margin-bottom: 8px;
        }
        & .container-for-form-description {
            padding-left: 46px;
            color: rgb(111, 108, 144);
            font-size: 18px;
            font-weight: 400;
            line-height: 30px;
            text-align: left;
            height: 30px;
            margin-bottom: 39px;
        }
    }
</style>