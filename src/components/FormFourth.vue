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
                <div><div></div></div>
                <div>4</div>
            </div>
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
                <button class="button-submit" @click="objectToLocalStorage()">Submit</button>
            </div>
        </div>
        <div class="buttons-next-and-previous-flex">
            <button class="button-previous" @click="changeSlideBack()">Previous step</button>
        </div>
    </div>
</template>
<script>
    export default {
        props: {
            savedObject: Object
        },
        methods: {
            changeSlideBack() {
                this.$emit('changeslideback', 2)
            },
            objectToLocalStorage() {
                localStorage.setItem('saved', JSON.stringify(this.savedObject))
            }
        }
    }
</script>
<style scoped>
    .buttons-next-and-previous-flex {
        display: flex;
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
        }
    }
    .form-inside {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
    .container-for-form-full {
        display: flex;
        flex-direction: column;
        margin-left: 60px;
        & .container-for-form {
            width: 698px;
            height: 606px;
            border-radius: 48px;
            box-shadow: 0 6px 54px 0 rgba(20, 20, 43, 0.07);
            background: rgb(255, 255, 255);
        }
        & .container-for-form-numbers {
            box-sizing: border-box;
            column-gap: 18px;
            display: flex;        
            height: 34px;
            padding-top: 34px;
            padding-left: 89px;
            padding-bottom: 58px;
            & div:first-child, div:nth-child(3), div:nth-child(5), div:nth-child(7) {
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
            & div:nth-child(2) div, div:nth-child(4) div, div:nth-child(6) div  {
                width: 98px;
                height: 6px;
                border-radius: 40px;
                background: rgb(74, 58, 255);
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
            height: 35px;
            text-align: center;
        }
        & .container-for-form-description {
            color: rgb(111, 108, 144);
            font-size: 18px;
            font-weight: 400;
            line-height: 30px;
            margin-top: 5px;
            text-align: center;
            width: 463px;
            margin-left: auto;
            margin-right: auto;
            margin-bottom: 24px;
        }
        & .picture {
            display: flex;
            justify-content: center;
            margin-bottom: 16px;
        }
        & .button-submit {
		    border-radius: 48px;
            box-shadow: 0px 2.59px 10.34px 0px rgba(74, 58, 255, 0.18);
            background: rgb(74, 58, 255);
            width: 139.33px;
            height: 52.58px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: rgb(255, 255, 255);
            font-size: 16px;
            font-weight: 700;
            line-height: 17px;
            letter-spacing: 0px;
            text-align: center;
            border: none;
        }
    }
</style>