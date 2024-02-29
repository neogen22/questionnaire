<template>
    <div class="container-for-form-full">
        <span>Get a project quote</span>
        <span>Please fill the form below to receive a quote for your project. Feel free to add as much detail as needed.</span>
        <div class="container-for-form">
            <StepperComponent pageNumber="pageFourth"/>
            <hr>
            <div class="form-inside">
                <div class="picture">
                    <svg width="135.644287" height="123.623535" viewBox="0 0 135.644 123.624" fill="none" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
                        <defs/>
                        <g opacity="0.500000">
                            <rect id="Rectangle 4343" x="12.110107" rx="8.620032" width="44.429966" height="44.429966" fill="#9E96FF" fill-opacity="1.000000"/>
                        </g>
                        <g opacity="0.500000">
                            <rect id="Rectangle 4345" x="110.336426" y="28.333984" rx="8.620032" width="25.307875" height="25.307875" fill="#9E96FF" fill-opacity="1.000000"/>
                        </g>
                        <g opacity="0.500000">
                            <rect id="Rectangle 4344" y="64.538086" rx="6.896026" width="27.181484" height="27.181484" fill="#DEDBFF" fill-opacity="1.000000"/>
                        </g>
                        <g opacity="0.500000">
                            <rect id="Rectangle 4346" x="98.515869" y="92.080078" rx="6.896026" width="31.543692" height="31.543692" fill="#DEDBFF" fill-opacity="1.000000"/>
                        </g>
                        <circle id="Ellipse 446" cx="71.957031" cy="67.559570" r="51.720192" fill="#4A3AFF" fill-opacity="1.000000"/>
                        <path id="Vector" d="M52.3757 70.3579L63.5649 81.5474L91.5381 53.5742" stroke="#FFFFFF" stroke-opacity="1.000000" stroke-width="6.896026" stroke-linejoin="round" stroke-linecap="round"/>
                    </svg>
                </div>  
                <div class="container-for-form-header">Submit your quote request</div>
                <div class="container-for-form-description">Please review all the information you previously typed in the past steps, and if all is okay, submit your message to receive a project quote in 24 - 48 hours.</div>
                    <button class="button-submit" @click="objectToLocalStorage()" v-if="!clicked">Submit</button>
                    <button class="button-submit" v-if="clicked">
                        <svg width="48" height="45" viewBox="0 0 53.4645 40.4668" fill="none" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">	
                            <defs/>
	                        <path id="Vector" d="M4.01636 23.4863L16.9969 36.4668L49.4482 4.01562" stroke="#FFFFFF" stroke-opacity="1.000000" stroke-width="8.000000" stroke-linejoin="round" stroke-linecap="round"/>
                        </svg>
                    </button>
                </div>
        </div>
        <div class="buttons-next-and-previous-flex">
            <ButtonComponent nameOfComponentTo="FormThird" buttonCSSType="button-previous" buttonText="Previous step"/>
        </div>
    </div>
</template>
<script>
    import ButtonComponent from './ButtonComponent.vue';
    import StepperComponent from './StepperComponent.vue';
    export default {
        inject: ['superObject'],
        components: {
            ButtonComponent,
            StepperComponent
        },
        data() {
            return {
                clicked: false
            }
        },
        methods: {
            objectToLocalStorage() {
                localStorage.setItem('saved', JSON.stringify(this.superObject))
                this.clicked = true
            }
        }
    }
</script>
<style scoped>
    .form-inside {
        align-items: center;
        display: flex;
        flex-direction: column;
        justify-content: center;
    }
    .container-for-form-full {
        display: flex;
        flex-direction: column;
        & .container-for-form {
            background: rgb(255, 255, 255);
            border-radius: 48px;
            box-shadow: 0 6px 54px 0 rgba(20, 20, 43, 0.07);
            min-height: 606.6px;
            width: 698px;
        }
        & span:first-child {
            color: rgb(23, 15, 73);
            display: block;
            font-family: 'DM Sans';
            font-size: 34px;
            font-weight: 700;
            line-height: 46px;
            margin-bottom: 12px;
            text-align: center;
            width: 680px;
        }
        & span:nth-child(2) {
            color: rgb(111, 108, 144);
            display:block;
            font-family: 'DM Sans';
            font-size: 18px;
            font-weight: 400;
            line-height: 30px;
            margin-left: 82px;
            margin-bottom: 42px;
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
            text-align: center;
        }
        & .container-for-form-description {
            color: rgb(111, 108, 144);
            font-family: 'DM Sans';
            font-size: 18px;
            font-weight: 400;
            line-height: 30px;
            margin-bottom: 24px;
            margin-left: auto;
            margin-right: auto;
            margin-top: 5px;
            text-align: center;
            width: 463px;
        }
        & .picture {
            display: flex;
            justify-content: center;
            margin-bottom: 16px;
        }
        & .button-submit {
            align-items: center;
            background: rgb(74, 58, 255);
            border: none;
		    border-radius: 48px;
            box-shadow: 0px 2.59px 10.34px 0px rgba(74, 58, 255, 0.18);
            color: rgb(255, 255, 255);
            cursor: pointer;
            display: flex;
            font-family: 'DM Sans';
            height: 53px;
            justify-content: center;            
            font-size: 16px;
            font-weight: 700;
            letter-spacing: 0px;
            line-height: 17px;
            text-align: center;
            transition: all 200ms;
            width: 139px;            
            -webkit-tap-highlight-color: rgba(0, 0, 0, 0)
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
            }
            & span:first-child {
                color: rgb(23, 15, 73);
                display: block;
                font-family: 'DM Sans';
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
                display:block;
                font-family: 'DM Sans';
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
                font-family: 'DM Sans';
                font-size: 21px;
                padding-left: 22px;
            }
            & .container-for-form-description {
                color: rgb(111, 108, 144);
                font-family: 'DM Sans';
                height: 50px;
                margin-bottom: 39px;
                max-width: 320px;
                font-size: 18px;
                font-weight: 400;
                letter-spacing: 0%;
                line-height: 30px;
                padding-left: 22px;
                text-align: left;
            }
            & .form {
                display: grid;
                grid-template-columns: 200px;
                row-gap: 24px;
            }
            & .button-submit {
                align-items: center;
                background: rgb(74, 58, 255);
                border: none;
                border-radius: 48px;
                box-shadow: 0px 2.59px 10.34px 0px rgba(74, 58, 255, 0.18);
                color: rgb(255, 255, 255);
                cursor: pointer;
                display: flex;
                font-family: 'DM Sans';
                font-size: 16px;
                font-weight: 700;
                height: 48px;
                justify-content: center;
                letter-spacing: 0px;
                line-height: 17px;                
                margin-top: 65px;
                text-align: center;
                width: 130px;
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