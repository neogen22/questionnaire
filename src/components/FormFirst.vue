<template>
    <div class="container-for-form-full">
        <span>Get a project quote</span>
        <span>Please fill the form below to receive a quote for your project. Feel free to add as much detail as needed.</span>
        <div class="container-for-form">
            <StepperComponent pageNumber="pageFirst"/>
            <hr>
            <div class="container-for-form-header">Contact details</div>
            <div class="container-for-form-description">Please fill your information so we can get in touch with you.</div>
            <div class="form">
                <InputComponent formPlaceholder="John Carter" formName="Name" formImageSource="man.svg" @customChange="saveName" :value="personName"/>
                <InputComponent formPlaceholder="Email address" formName="Email" formImageSource="email.svg" @customChange="saveEmail" :value="email"/>
                <InputComponent formPlaceholder="Phone number" formName="Phone" formImageSource="phone.svg" @customChange="savePhone" :value="phone"/>
                <InputComponent formPlaceholder="Company name" formName="Company" formImageSource="company.svg" @customChange="saveCompany" :value="company"/>
            </div>
        </div>
        <div class="buttons-next-and-previous-flex">
            <ButtonComponent nameOfComponentTo="FormSecond" buttonCSSType="button-next" buttonText="Next step"/>
        </div>
    </div>
</template>
<script>
    import InputComponent from './InputComponent.vue'
    import ButtonComponent from './ButtonComponent.vue'
    import StepperComponent from './StepperComponent.vue'
    export default {
        components: {
            InputComponent,
            ButtonComponent,
            StepperComponent,    
        },
        inject: ['superObject'],
        data() {
            return {
                personName: this.superObject?.personName ? this.superObject.personName : '',
                email: this.superObject?.email ? this.superObject.email : '',
                phone: this.superObject?.phone ? this.superObject.phone : '',
                company: this.superObject?.company ? this.superObject.company : '',
            }
        },
        methods: {
            saveName(event) {
                this.personName = event                
            },
            saveEmail(event) {
                this.email = event
            },
            saveCompany(event) {
                this.company = event
            },
            savePhone(event) {
                this.phone = event
            }
        },
        beforeUnmount() {
            this.superObject.personName = this.personName
            this.superObject.email = this.email
            this.superObject.company = this.company
            this.superObject.phone = this.phone
        }
    }
</script>
<style scoped>
    .container-for-form-full {
        display: flex;
        flex-direction: column;
        & .container-for-form {
            background: rgb(255, 255, 255);
            border-radius: 48px;
            box-shadow: 0px 6px 54px 0px rgba(20, 20, 43, 0.07);
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
            color: rgb(23, 15, 73);
            display: block;
            font-size: 34px;
            font-weight: 700;
            letter-spacing: 0%;
            line-height: 46px;
            margin-bottom: 12px;
            text-align: center;
            width: 680px;
        }
        & span:nth-child(2) {
            display:block;
            color: rgb(111, 108, 144);
            font-size: 18px;
            font-weight: 400;
            letter-spacing: 0%;
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
            letter-spacing: 0%;
            line-height: 35px;
            margin-bottom: 8px;
            padding-left: 46px;
        }
        & .container-for-form-description {
            color: rgb(111, 108, 144);            
            font-size: 18px;
            font-weight: 400;
            height: 30px;
            letter-spacing: 0%;
            line-height: 30px;
            margin-bottom: 39px;
            padding-left: 46px;
            text-align: left;
        }
        & .buttons-next-and-previous-flex {
            display: flex;
            flex-direction: row;
            justify-content: flex-end;
        }
    }
    @media (width <= 760px) {        
        .container-for-form-full {
            width: 300px;            
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
                line-height: 20px;
                letter-spacing: 0%;
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
            & .container-for-form {
                background: rgb(255, 255, 255);
                border-radius: 48px;
                box-shadow: 0px 6px 54px 0px rgba(20, 20, 43, 0.07);
                min-height: 500px;
                padding-bottom: 0px;
                width: 334px;
            }
            & .form {
                display: grid;
                grid-template-columns: 265px;
                row-gap: 24px;
                margin-top: 50px;
            }
        }
        .buttons-next-and-previous-flex {
            display: flex;
            flex-direction: row;
            justify-content: flex-end;
            width: 334px
        }
    }
</style>