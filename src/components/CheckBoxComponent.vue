<template>
    <label :class="{checkBoxActive: activeCheckBox}">
        <input type="checkbox" :id="name" @click="toggleCheckBox()"  @change="$emit('update:modelValue', $event.target.checked)" :value="modelValue">
        <img :src="checkBoxImageSource">
        <div>{{ name }}</div>
    </label>
</template>
<script>
    export default {
        inject: ['superObject'],
        props: {
            name: {
                type: String,
                required: true
            },            
            checkBoxImageSource: {
                type: String,
                required: true
            },
            modelValue: {
                type: Boolean,
                required: true
            }
        },
        data() {
            return {
                activeCheckBox: this.superObject.services === undefined ? false : this.superObject.services.includes(this.name),
                image: new URL(`/public/${this.formImageSource}`, import.meta.url).href,
                servicesComponent: ''
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
        align-items: center;
        box-sizing: border-box;
        border: 1px solid rgb(239, 240, 247);
		border-radius: 16px;
        box-shadow: 0 2px 6px 0 rgba(19, 18, 66, 0.07);
        background: rgb(255, 255, 255);
        display: flex;
        height: 115px;
        padding-left: 26px;
        transition-property: border-color;
        transition-duration: 0.5s;
        & div {
            color: rgb(23, 15, 73);
            font-family: 'DM Sans';
            font-size: 18px;
            font-weight: 500;
            line-height: 20px;
            padding-left: 12px;
        }
    }
    .checkBoxActive {
        outline: 2px solid rgb(74, 58, 255);
    }
    @media (width <= 760px) {
        label {
            height: 45px;
            margin-left: -25px
        }
        img {
            height: 33px;
            width: 33px;
        }
    }
</style>