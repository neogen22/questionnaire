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
                <InputComponent formPlaceholder="John Carter" formName="Name" formImageSource="\public\man.svg" @customChange="saveName" :value="personName"/>
                <InputComponent formPlaceholder="Email address" formName="Email" formImageSource="\public\email.svg" @customChange="saveEmail" :value="email"/>
                <InputComponent formPlaceholder="Phone number" formName="Phone" formImageSource="\public\phone.svg" @customChange="savePhone" :value="phone"/>
                <InputComponent formPlaceholder="Company name" formName="Company" formImageSource="\public\company.svg" @customChange="saveCompany" :value="company"/>
            </div>
        </div>
        <ButtonComponent nameOfComponentTo="FormSecond" buttonCSSType="button-next" buttonText="Next step"/>
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
        margin-left: 60px;
        & .container-for-form {
            width: 698px;
            min-height: 606px;
            border-radius: 48px;
            box-shadow: 0px 6px 54px 0px rgba(20, 20, 43, 0.07);
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
            letter-spacing: 0%;
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
            letter-spacing: 0%;
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
            letter-spacing: 0%;
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
            letter-spacing: 0%;
            text-align: left;
            height: 30px;
            margin-bottom: 39px;
        }
    }
</style>