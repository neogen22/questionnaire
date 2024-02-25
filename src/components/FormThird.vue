<template>
    <div class="container-for-form-full">
        <span>Get a project quote</span>
        <span>Please fill the form below to receive a quote for your project. Feel free to add as much detail as needed.</span>
        <div class="container-for-form">
            <StepperComponent pageNumber="pageThird"/>
            <hr>
            <div class="container-for-form-header">What’s your project budget?</div>
            <div class="container-for-form-description">Please select the project budget range you have in mind.</div>
            <div class="form">
                <div class="form-container-page-2">
                    <RadioComponent v-for="(i, y) in values"  :key="values[y]"
                        :value = i
                        @activate-radio-button="receive"
                        :class="{'selected': this.check === i}"
                        :active="this.check === i"
                    />
                </div>
            </div>
        </div>
        <div class="buttons-next-and-previous-flex">
            <ButtonComponent nameOfComponentTo="FormSecond" buttonCSSType="button-previous" buttonText="Previous step"/>
            <ButtonComponent nameOfComponentTo="FormFourth" buttonCSSType="button-next" buttonText="Next step"/>
        </div>
    </div>
</template>

<script>
    import RadioComponent from './RadioComponent.vue'
    import ButtonComponent from './ButtonComponent.vue'
    import StepperComponent from './StepperComponent.vue'
    export default {
        inject: ['superObject'],
        components: {
            RadioComponent,
            ButtonComponent,
            StepperComponent,    
        },
        data() {
            return {
                check: this.superObject.budget ? this.superObject.budget : '',
                values: ['$5.000 - $10.000', '$10.000 - $20.000', '$20.000 - $50.000', '$50.000 +']
            }
        },
        methods: {
            receive(event) {
                this.check = event
            },
        },
        beforeUnmount() {
            this.superObject.budget = this.check
        }
    }
</script>

<style scoped>
    .selected {
        border: 2px solid rgb(74, 58, 255);
    } 
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
    .buttons-next-and-previous-flex {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
    }
    .form-container-page-2 {
        display: grid;
        grid-template-columns: 284px 284px;
        column-gap: 28px;
        row-gap: 21px;
    }
    .container-for-form-full {
        display: flex;
        flex-direction: column;
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
    @media (width <= 760px) {        
        .container-for-form-full {
            width: 300px;
            & .container-for-form {
                width: 334px;
                min-height: 500px;
                border-radius: 48px;
                box-shadow: 0px 6px 54px 0px rgba(20, 20, 43, 0.07);
                background: rgb(255, 255, 255);
                padding-bottom: 0px;
            }
            & span:first-child {
                display: block;
                color: rgb(23, 15, 73);
                font-size: 24px;
                font-weight: 700;
                line-height: 46px;
                letter-spacing: 0%;
                text-align: center;
                max-width: 320px;            
                margin-bottom: 6px;
            }
            & span:nth-child(2) {
                display:block;
                color: rgb(111, 108, 144);
                font-size: 14px;
                font-weight: 400;
                line-height: 20px;
                letter-spacing: 0%;
                text-align: center;
                max-width: 320px;
                margin-left: 0px;
                margin-bottom: 16px;
            }
            & hr {
                width: 300px;
                border: 1px solid rgb(217, 219, 233);
                margin-bottom: 16px;
                margin-left: 20px;
            }            
            & .container-for-form-header {
                padding-left: 22px;
                font-size: 21px;
            }
            & .container-for-form-description {
                padding-left: 22px;
                max-width: 320px;
                color: rgb(111, 108, 144);
                font-size: 18px;
                font-weight: 400;
                line-height: 30px;
                letter-spacing: 0%;
                text-align: left;
                height: 50px;
                margin-bottom: 39px;
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
        .form-container-page-2 {
            grid-template-columns: 264px;
        }
    }
</style>