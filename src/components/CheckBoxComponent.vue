<template>
    <label :class="{checkBoxActive: activeCheckBox}">
        <input type="checkbox" :id="name" @click="toggleCheckBox()">
        <img :src="checkBoxImageSource">
        <div>{{ name }}</div>
    </label>
</template>
<script>
    export default {
        inject: ['superObject'],
        props: {
            name: String,            
            checkBoxImageSource: String
        },
        data() {
            return {
                image: new URL(`/public/${this.formImageSource}`, import.meta.url).href,
                activeCheckBox: this.superObject.services === undefined ? false : this.superObject.services.includes(this.name)
            }
        },
        methods: {
            toggleCheckBox() {
                this.activeCheckBox = !this.activeCheckBox
                if (this.activeCheckBox) {
                    if (this.superObject.services === undefined || !this.superObject.services.includes(this.name)) {
                        if (this.superObject.services === undefined) {
                            this.superObject.services = []
                            this.superObject.services.push(this.name)
                        } else {
                            this.superObject.services.push(this.name)
                        }
                    }                    
                } else {
                    this.superObject.services.splice(this.superObject.services.findIndex(e => e === this.name), 1)
                }                
            }
        }
    }
</script>
<style scoped>
    input[type="checkbox"] {
        appearance: none;
    }
    label {
        padding-left: 26px;
        box-sizing: border-box;
        border: 1px solid rgb(239, 240, 247);
		border-radius: 16px;
        box-shadow: 0 2px 6px 0 rgba(19, 18, 66, 0.07);
        background: rgb(255, 255, 255);
        height: 115px;
        display: flex;
        align-items: center;
        transition-property: border-color;
        transition-duration: 0.5s;
        & div {
            color: rgb(23, 15, 73);
            font-size: 18px;
            font-weight: 500;
            line-height: 20px;
            padding-left: 12px;
        }
    }
    .checkBoxActive {
        border: 2px solid rgb(74, 58, 255);
    }
</style>