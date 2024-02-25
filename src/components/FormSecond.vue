<template>
    <div class="container-for-form-full">
        <span>Get a project quote</span>
        <span>Please fill the form below to receive a quote for your project. Feel free to add as much detail as needed.</span>
        <div class="container-for-form">
            <StepperComponent pageNumber="pageSecond"/>
            <hr>
            <div class="container-for-form-header">Our services</div>
            <div class="container-for-form-description">Please select which service you are interested in.</div>
            <div class="form">
                <div class="form-container-page-2">
                    <CheckBoxComponent name="Development" checkBoxImageSource="developmentIcon.svg"/>
                    <CheckBoxComponent name="Web Design" checkBoxImageSource="WebDesignIcon.svg" />
                    <CheckBoxComponent name="Marketing" checkBoxImageSource="marketing.svg" />
                    <CheckBoxComponent name="Other" checkBoxImageSource="other.svg" />
                </div>
            </div>
        </div>
        <div class="buttons-next-and-previous-flex">            
            <ButtonComponent nameOfComponentTo="FormFirst" buttonCSSType="button-previous" buttonText="Previous step"/>
            <ButtonComponent nameOfComponentTo="FormThird" buttonCSSType="button-next" buttonText="Next step"/>
        </div>
    </div>
</template>
<script>
    import CheckBoxComponent from './CheckBoxComponent.vue'
    import ButtonComponent from './ButtonComponent.vue';
    import StepperComponent from './StepperComponent.vue';
    export default {
        inject: ['superObject'],
        components: {
            CheckBoxComponent,
            ButtonComponent,
            StepperComponent
        },
    }    
</script>
<style scoped>
    .buttons-next-and-previous-flex {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
    }
    .form-container-page-2 {
        column-gap: 28px;
        display: grid;
        grid-template-columns: 284px 284px;
        row-gap: 21px;
        & > div {
            align-items: center;
            background: rgb(255, 255, 255);
            border: 1px solid rgb(239, 240, 247);
			border-radius: 16px;
            box-shadow: 0 2px 6px 0 rgba(19, 18, 66, 0.07);
            box-sizing: border-box;
            display: flex;
            height: 115px;
            padding-left: 26px;
            transition-duration: 0.5s;
            transition-property: border-color;
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
        & .container-for-form {
            background: rgb(255, 255, 255);
            border-radius: 48px;
            box-shadow: 0 6px 54px 0 rgba(20, 20, 43, 0.07);
            min-height: 606px;
            min-width: 698px;
            padding-bottom: 86px;
        }
        & .form {
            column-gap: 28px;
            display: grid;
            grid-template-columns: 284px 284px;
            margin-left: 46px;
            row-gap: 44px;
        }
        & span:first-child {
            color: rgb(23, 15, 73);
            display: block;
            font-size: 34px;
            font-weight: 700;
            line-height: 46px;
            margin-bottom: 12px;
            text-align: center;
            width: 680px;
        }
        & span:nth-child(2) {
            color: rgb(111, 108, 144);
            display: block;
            font-size: 18px;
            font-weight: 400;
            line-height: 30px;
            margin-bottom: 42px;
            margin-left: 82px;
            text-align: center;
            width: 517px;
        }
        & hr {
            border: 1px solid rgb(217, 219, 233);
            margin-bottom: 64px;
            margin-left: 50px;
            width: 596px;
        }
        & .container-for-form-header {
            color: rgb(23, 15, 73);
            font-size: 24px;
            font-weight: 700;
            height: 35px;
            line-height: 35px;
            margin-bottom: 8px;
            padding-left: 46px;
        }
        & .container-for-form-description {
            color: rgb(111, 108, 144);
            font-size: 18px;
            font-weight: 400;
            line-height: 30px;
            height: 30px;
            margin-bottom: 39px;
            padding-left: 46px;
            text-align: left;
        }
    }
    @media (width <= 760px) {        
        .container-for-form-full {
            width: 300px;
            & .container-for-form {
                background: rgb(255, 255, 255);
                border-radius: 48px;
                box-shadow: 0px 6px 54px 0px rgba(20, 20, 43, 0.07);
                min-height: 500px;
                min-width: 334px;
                padding-bottom: 0px;
            }
            & span:first-child {
                color: rgb(23, 15, 73);
                display: block;
                font-size: 24px;
                font-weight: 700;
                letter-spacing: 0%;
                line-height: 46px;
                margin-bottom: 6px;
                max-width: 320px; 
                text-align: center;
            }
            & span:nth-child(2) {
                color: rgb(111, 108, 144);
                display: block;
                font-size: 14px;
                font-weight: 400;
                letter-spacing: 0%;
                line-height: 20px;
                margin-bottom: 16px;
                margin-left: 0px;
                max-width: 320px;
                text-align: center;
            }
            & hr {                
                border: 1px solid rgb(217, 219, 233);
                margin-bottom: 16px;
                margin-left: 20px;
                width: 300px;
            }            
            & .container-for-form-header {
                font-size: 21px;
                padding-left: 22px;
            }
            & .container-for-form-description {
                color: rgb(111, 108, 144);
                height: 50px;
                font-size: 18px;
                font-weight: 400;
                line-height: 30px;
                letter-spacing: 0%;
                margin-bottom: 39px;
                max-width: 320px;
                padding-left: 22px;
                text-align: left;
            }
            & .form {
                display: grid;
                grid-template-columns: 200px;
                row-gap: 24px;
            }
        }
        .buttons-next-and-previous-flex {
            display: flex;
            flex-direction: row;
            justify-content: space-between;
            width: 334px
        }
        & .form-container-page-2 {
            grid-template-columns: 264px;
        }
    }
</style>