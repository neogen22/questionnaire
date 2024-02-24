<template>
    <div :class="pageNumber">
        <div><div>1</div></div>
        <div><div></div></div>
        <div>2</div>
        <div><div v-if="pageNumber !== 'pageFirst'"></div></div>
        <div>3</div>
        <div><div v-if="pageNumber !== 'pageFirst' && pageNumber !== 'pageSecond'"></div></div>
        <div>4</div>
    </div>
</template>

<script>
    export default {
        props: {
            pageNumber: {
                type: String,
                required: true
            }
        }
    }
</script>
<style scoped>
    .pageFirst {        
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
    .pageSecond {        
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
    .pageThird {
        box-sizing: border-box;
        column-gap: 18px;
        display: flex;        
        height: 34px;
        padding-top: 34px;
        padding-left: 89px;
        padding-bottom: 58px;
        & div:first-child, div:nth-child(3), div:nth-child(5) {
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
        & div:nth-child(2) div, div:nth-child(4) div {
            width: 98px;
            height: 6px;
            border-radius: 40px;
            background: rgb(74, 58, 255);
        }
        div:nth-child(6) div {
            width: 49px;
            height: 6px;
            border-radius: 40px;
            background: rgb(74, 58, 255);
        }
        & div:nth-child(7) {
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
    .pageFourth {
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
</style>