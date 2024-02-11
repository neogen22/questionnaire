<template>
    <body>
        <div class="header">
            <div class="header-brix-template">
                <div class="rounds-grid-container">
                    <svg viewBox="0 0 100 100">
                        <circle cx="50" cy="50" r="50" />
                    </svg>
                    <svg viewBox="0 0 100 100">
                        <circle cx="50" cy="50" r="50" />
                    </svg>
                    <svg viewBox="0 0 100 100">
                        <circle cx="50" cy="50" r="50" />
                    </svg>
                    <svg viewBox="0 0 100 100">
                        <circle cx="50" cy="50" r="50" />
                    </svg>
                    <svg viewBox="0 0 100 100">
                        <circle cx="50" cy="50" r="50" />
                    </svg>
                    <svg viewBox="0 0 100 100">
                        <circle cx="50" cy="50" r="50" />
                    </svg>
                </div>
                <div class="brix_template_container">
                    <div>
                        <img src="\public\brix.svg">
                    </div>
                    <div>
                        <img src="\public\templates.svg">
                    </div>
                </div>        
            </div>
            <div class="button-clone">Clone now</div>
        </div>
        <div class="hero-container">        
            <div>Cloneables FOR WEBFLOW</div>
            <div class="hero-header">Multi-step Form Webflow Cloneable Template</div>
            <div class="subscribe-container">
                <span class="subscribe-container-text">Want to receive a monthly email in your inbox with awesome free Webflow cloneables, resources and more? Please submit your email below.</span>
                <div class="button-email"><span>Enter your email</span><div class="button-subscribe">Subscribe</div></div>
                <div class="subscribe-footer">
                    <img src="\public\galka.svg">
                    <div> It's <span>100% free</span> and we will never send more than one email per month</div>
                </div>    
            </div>        
        </div>
        <div class="multi-step-form-step-1"><span>Multi Step Form - Step {{ count + 1 }}</span><span>Preview Cloneable</span></div>        
        <FormFirst @changeslide="count = $event" v-if="count === 0"/>
        <FormSecond @changeslide="count = $event" @changeslideback="count = $event" v-if="count === 1"/>
        <FormThird @changeslide="count = $event" @changeslideback="count = $event" v-if="count === 2"/>
        <FormFourth @changeslideback="count = $event" v-if="count === 3"/>
    </body>
</template>

<script>
import FormFirst from './components/FormFirst.vue';
import FormSecond from './components/FormSecond.vue';
import FormThird from './components/FormThird.vue'
import FormFourth from './components/FormFourth.vue'
export default {
    components: {
        FormFirst,
        FormSecond,
        FormThird,
        FormFourth
    },
    provide: {
        superObject: {}
    },
    data() {
        return {
            count: 0,
        }
    }
}

</script>

<style scoped>
    body {
        flex-direction: column;
    }
    .multi-step-form-step-1 {
        width: 1242px;
        height: 108px;
        box-shadow: 0px 12px 24px 0px rgba(20, 20, 43, 0.04),0px -2px 4px 0px rgba(20, 20, 43, 0.02),0px 3px 14px 0px rgba(74, 58, 255, 0.03);
        border-radius: 18px;
        margin-bottom: 171px;
        & span:first-child {
            display: inline-block;
            padding-top: 36px;
            padding-left: 32px;
            color: rgb(23, 15, 73);
            font-size: 24px;
            font-weight: 700;
            line-height: 35px;
            letter-spacing: 0%;
        }
        & span:nth-child(2) {
            color: rgb(74, 58, 255);
            font-size: 16px;
            font-weight: 500;
            line-height: 18px;
            letter-spacing: 0%;
            margin-left: 738px;
            background: rgb(243, 241, 255);
            width: 195px;
            text-align: center;
            padding: 16px 28px 17px 28px;
            border-radius: 50px;
        }
    }
    .subscribe-container {
        padding-top: 13px;
        & .subscribe-container-text {
            display: block;
            color: rgb(111, 108, 144);
            font-size: 18px;
            font-weight: 400;
            line-height: 30px;
            letter-spacing: 0%;
            text-align: center;
            width: 680px;            
        }
        & div:nth-child(3) {
            margin-left: 110px;
        }
        & .subscribe-footer {
            display: flex;
            flex-direction: row;
            padding-top: 25px;
            gap: 8px;
            & div {
                color: rgb(111, 108, 144);
                font-size: 16px;
                font-weight: 400;
                line-height: 23px;
                letter-spacing: 0px;
                text-align: center;
                & span {
                    color: rgb(74, 58, 255)
                }
            }
        }
    }
    .hero-container {
        width: 680px;
        height: 401px;
        margin-top: 40px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        padding-bottom: 100px;
        & div:first-child {
            width: 300px;
            height: 18px;
            font-size: 16px;
            font-weight: 500;
            color: rgb(74, 58, 255);
            text-transform: uppercase;
            line-height: 18px;
            letter-spacing: 24%;
            padding-left: 50px;
            align-self: center;
        }
        & .hero-header {
            padding-top: 12px;
            width: auto;
            height: 124px;
            color: rgb(23, 15, 73);
            font-size: 50px;
            font-weight: 700;
            line-height: 62px;
            letter-spacing: 0px;
            text-align: center;
            justify-self: center;
        }
        & .button-email {
            box-sizing: border-box;
            display: flex;
            height: 78px;
            border-radius: 60px;        
            font-size: 18px;        
            box-sizing: border-box;
            margin-top: 40px;
            margin-left: 75px;
            border-radius: 60px;
            box-shadow: 0px 8px 25px 0px rgba(13, 10, 44, 0.06);        
            & span {
                padding-top: 26px;
                color: rgb(111, 108, 144);
                margin-left: 30px;
                
            }
            & .button-subscribe {
                background-color: rgb(74, 58, 255);
                width: 153px;
                height: 55px;
                align-self: center;
                border-radius: 56px;
                padding: 16px 32px 19px 32px;
                margin-right: 16px;
                box-sizing: border-box; 
                color: rgb(255, 255, 255);
                font-size: 18px;
                font-weight: 700;
                text-align: center;
                margin-left: 270px;
            }
        }    
    }    
    .header {
        display: flex;
        max-width: 1440px;
        margin-left: 100px;
        margin-right: 100px;
        column-gap: 765px;
    }
    .rounds-grid-container {
        display: grid;
        grid-template-columns: 12px 12px 12px;
        width: 41px;
        height: 41px;
        place-items: center;
        gap: 2px;
        & svg {
            width: 12px;
            height: 12px;
            fill: rgb(106, 74, 252);
        }
        & svg:nth-child(1){
            grid-column: 1 / span 3;
            justify-self: end;
        }
        & svg:nth-child(2){
            grid-column: 1 / span 2;
            justify-self: end;
        }
    }
    .header-brix-template{
        display: flex;
        width: 305px;
        gap: 15px;
        padding-top: 42px;
        padding-bottom: 44px;
    }
    .brix_template_container {
        display: flex;
        width: 248px;
        gap: 8px;        
        & div:first-child {
            width: 67px;
            align-self: center;
        }
        & div:nth-child(2) {
            width: 174px;
            padding-top: 5px;
        }
    }
    .button-clone {
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
    }
</style>
