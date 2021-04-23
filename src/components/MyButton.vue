<template>
    <button :class="addClass" :style="addStyle" @click="onClick"><slot>확인</slot></button>
</template>

<script>
export default {
    name: 'MyButton',

    data() {
        return {
            CLASS_NAME: 'pyo-bt'
        }
    },

    props: {
        size: {
            type: String,
            default: 'medium',
        },
        font_size: {
            type: String,
            default: '',
        },
        font_weight: {
            type: String,
            default: '',
        },
        font_color: {
            type: String,
            default: '',
        },
        border_color: {
            type: String,
            default: '',
        },
        border_size: {
            type: String,
            default: '',
        },
        fill: {
            type: Boolean,
            default: false,
        },
        fill_color: {
            type: String,
            default: '',
        },
        padding: {
            type: String,
            default: '',
        },
        
    },

    computed: {
        addClass() {
            return {
                [this.CLASS_NAME] : true,
                [this.CLASS_NAME + '-fill'] : this.fill,
                [this.CLASS_NAME + '-' + this.size] : ['small', 'large'].indexOf(this.size) !== -1,
            };
        },
        addStyle() {
            return {
                'padding': this.padding,
                'border-color': this.border_color || this.fill_color,
                'border-width': this.border_size,
                'background': this.fill_color,
                'font-size': this.font_size,
                'font-weight': this.font_weight,
                'color': this.font_color,
            };
        },
    },

    methods: {
        onClick() {
            this.$emit('onClick');
        }
    },
}
</script>

<style lang="scss" scoped>
$class-name: 'pyo-bt';
.#{$class-name}{
    line-height: 1;
    padding: 10px 15px;
    border-radius: 5px;
    border: 1px solid #ddd;
    background-color: transparent;
    color: #000;
    font-size: 14px;
    outline: 0;
    cursor: pointer;
    &.#{$class-name}-fill{
        border-color: #000;
        background-color: #000;
        color: #fff;
    }
    &.#{$class-name}-small{
        padding: 5px 10px;
        font-size: 12px;
    }
    &.#{$class-name}-large{
        padding: 12px 25px;
        font-size: 16px;
    }
}
</style>