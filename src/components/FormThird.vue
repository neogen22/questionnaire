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
            <div class="failed" v-if="formThirdFail">Please, select one option</div>
        </div>
        <div class="buttons-next-and-previous-flex">
            <ButtonComponent nameOfComponentTo="FormSecond" buttonCSSType="button-previous" buttonText="Previous step"/>
            <ButtonComponent nameOfComponentTo="FormFourth" buttonCSSType="button-next" buttonText="Next step" @click="checkRadio()"/>
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
                values: ['$5.000 - $10.000', '$10.000 - $20.000', '$20.000 - $50.000', '$50.000 +'],
                formThirdFail: false
            }
        },
        methods: {
            receive(event) {
                this.check = event
            },
            checkRadio() {
                if (this.check === '') {
                    this.$root.dynamicComponent = 'FormThird'
                    this.formThirdFail = true
                }
            }
        },
        watch: {
            check() {
                if (this.check !== '') {
                    this.formThirdFail = false
                }
            }
        },
        beforeUnmount() {
            this.superObject.budget = this.check            
        }
    }
</script>

<style scoped>
    .selected {
        outline: 2px solid rgb(74, 58, 255);
    } 
    label {
        color: rgb(23, 15, 73);
        font-size: 16px;
        font-weight: 400;
        letter-spacing: 2%;
        line-height: 17px;
        margin-left: 5px;
    }
    input[type='radio'] {
        border-radius: 50%;
        height: 17px;
        width: 17px;
    }
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
    }
    .container-for-form-full {
        display: flex;
        flex-direction: column;
        & .container-for-form {
            background: rgb(255, 255, 255);            
            border-radius: 48px;
            box-shadow: 0 6px 54px 0 rgba(20, 20, 43, 0.07);
            min-height: 606px;
            padding-bottom: 86px;
            width: 698px;
        }
        & .form {
            column-gap: 28px;
            display: grid;
            grid-template-columns: 284px 284px;
            margin-left: 46px;
            row-gap: 44px;
        }
        & span:first-child {
            display: block;
            color: rgb(23, 15, 73);
            font-family: 'DM Sans';
            font-size: 34px;
            font-weight: 700;
            line-height: 46px;
            margin-bottom: 12px;
            text-align: center;
            width: 680px;
        }
        & span:nth-child(2) {
            display:block;
            color: rgb(111, 108, 144);
            font-family: 'DM Sans';
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
            font-family: 'DM Sans';
            font-size: 24px;
            font-weight: 700;
            height: 35px;
            line-height: 35px;
            margin-bottom: 8px;
            padding-left: 46px;
        }
        & .container-for-form-description {            
            color: rgb(111, 108, 144);
            font-family: 'DM Sans';
            font-size: 18px;
            font-weight: 400;
            height: 30px;
            line-height: 30px;
            margin-bottom: 39px;
            padding-left: 46px;
            text-align: left;
        }
        & .failed {
            color: red;
            font-family: 'DM Sans';
            font-size: 25px;            
            margin-left: 170px;
            margin-top: 10px;
            position: absolute;
        }
        @-moz-document url-prefix() {
            & .failed {
                margin-top: 20px;
            }
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
                padding-bottom: 0px;
                width: 334px;
                & .failed {
                    color: red;
                    font-family: 'DM Sans';
                    font-size: 15px;
                    margin-left: 90px;
                    margin-top: 10px;
                    position: absolute;
                }
            }
            & span:first-child {
                display: block;
                color: rgb(23, 15, 73);
                font-family: 'DM Sans';
                font-size: 24px;
                font-weight: 700;
                line-height: 46px;
                letter-spacing: 0%;
                margin-bottom: 6px;
                max-width: 320px;
                text-align: center;
            }
            & span:nth-child(2) {
                display:block;
                color: rgb(111, 108, 144);
                font-family: 'DM Sans';
                font-size: 14px;
                font-weight: 400;
                line-height: 20px;
                letter-spacing: 0%;
                margin-left: 0px;
                margin-bottom: 16px;
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
                font-family: 'DM Sans';
                font-size: 21px;
                padding-left: 22px;
            }
            & .container-for-form-description {
                color: rgb(111, 108, 144);
                font-family: 'DM Sans';
                font-size: 18px;
                font-weight: 400;
                height: 50px;
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
        .form-container-page-2 {
            grid-template-columns: 264px;
        }
    }
</style>