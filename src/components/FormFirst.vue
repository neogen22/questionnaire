<template>
    <div class="container-for-form-full">
        <span>Get a project quote</span>
        <span>Please fill the form below to receive a quote for your project. Feel free to add as much detail as needed.</span>
        <div class="container-for-form">
            <div class="container-for-form-numbers">
                <div><div>1</div></div>
                <div><div></div></div>
                <div>2</div>
                <div></div>
                <div>3</div>
                <div></div>
                <div>4</div>
            </div>
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
        <button class="button-next" @click="changeSlide()">Next step</button>
    </div>
</template>
<script>
    import InputComponent from './InputComponent.vue'
    export default {
        components: {
            InputComponent    
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
            changeSlide() {
                this.superObject.personName = this.personName
                this.superObject.email = this.email
                this.superObject.company = this.company
                this.superObject.phone = this.phone
                this.$emit('changeslide', 1)
            },
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
        & .container-for-form-numbers {
            box-sizing: border-box;
            column-gap: 18px;
            display: flex;        
            height: 34px;
            padding-top: 34px;
            padding-left: 89px;
            padding-bottom: 58px;
            & div:first-child {
                display: flex;
                color: rgb(255, 255, 255);
                font-size: 16px;
                font-weight: 500;
                line-height: 18px;
                letter-spacing: 0%;
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
                width: 49px;
                height: 6px;
                border-radius: 40px;
                background: rgb(74, 58, 255);
            }
            & div:nth-child(3), div:nth-child(5), div:nth-child(7) {
                display: flex;
                color: rgb(111, 108, 144);
                font-size: 16px;
                font-weight: 500;
                line-height: 18px;
                letter-spacing: 0%;
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
            align-self: flex-end;
            border: none;
        }
    }
</style>