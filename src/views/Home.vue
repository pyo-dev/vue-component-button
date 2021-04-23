<template>
    <div class="wrap">
        <div class="box">
            <div class="title">slot</div>
            <MyButton />
            <MyButton>취소</MyButton>
        </div>
        <div class="box">
            <div class="title">size</div>
            <MyButton 
                :size="'small'"
            >small</MyButton>
            <MyButton>default</MyButton>
            <MyButton 
                :size="'large'"
            >large</MyButton>
        </div>
        <div class="box">
            <div class="title">font-size</div>
            <MyButton>default</MyButton>
            <MyButton 
                :font_size="'20px'"
            >20px</MyButton>
            <MyButton 
                :font_size="'2rem'"
            >2rem</MyButton>
        </div>
        <div class="box">
            <div class="title">font-weight</div>
            <MyButton>default</MyButton>
            <MyButton
                :font_weigth="'bold'"
            >bold</MyButton>
            <MyButton
                :font_weigth="'900'"
            >900</MyButton>
        </div>
        <div class="box">
            <div class="title">font-color</div>
            <MyButton>default</MyButton>
            <MyButton
                :font_color="'red'"
            >red</MyButton>
            <MyButton
                :font_color="'#777'"
            >#777</MyButton>
        </div>
        <div class="box">
            <div class="title">fill</div>
            <MyButton 
                :fill="true"
            ></MyButton>
            <MyButton 
                :fill="true"
                :fill_color="'red'"
            >red</MyButton>
            <MyButton 
                :fill="true"
                :fill_color="'#777'"
            >#777</MyButton>
        </div>
        <div class="box">
            <div class="title">border-color</div>
            <MyButton>default</MyButton>
            <MyButton 
                :border_color="'red'"
            >red</MyButton>
            <MyButton 
                :border_color="'#777'"
            >#777</MyButton>
        </div>
        <div class="box">
            <div class="title">border-size</div>
            <MyButton>default</MyButton>
            <MyButton 
                :border_size="'3px'"
            >3px</MyButton>
            <MyButton 
                :border_size="'1px 3px 3px 1px'"
            >1px 3px 3px 1px</MyButton>
        </div>
        <div class="box">
            <div class="title">padding</div>
            <MyButton>default</MyButton>
            <MyButton 
                :padding="'5px'"
            >5px</MyButton>
            <MyButton 
                :padding="'20px 40px'"
            >20px 40px</MyButton>
        </div>
        <div class="box">
            <div class="title">style total</div>
            <MyButton 
                :padding="'15px 25px'"
                :border_color="'#E65320'"
                :border_size="'1px 3px 3px 1px'"
                :fill_color="'#F07522'"
                :font_color="'#fff'"
                :font_weight="'bold'"
                :font_size="'18px'"
            ></MyButton>
            <MyButton 
                :padding="'15px 25px'"
                :border_color="'#061161'"
                :border_size="'1px 3px 3px 1px'"
                :fill_color="'linear-gradient(45deg, #061161, #780206)'"
                :font_color="'#fff'"
                :font_weight="'bold'"
                :font_size="'18px'"
            >취소</MyButton>
        </div>
        <div class="box">
            <div class="title">click</div>
            <MyButton @onClick="clickSuccess">success</MyButton>
            <MyButton @onClick="clickFail">fail</MyButton>
        </div>
    </div>
</template>

<script>
import MyButton from "@/components/MyButton";
export default {
    name: 'Home',

    components: {
        MyButton
    },

    methods: {
        clickSuccess() {
            alert('success');
        },
        clickFail(){
            alert('fail');
        }
    },
}
</script>

<style lang="scss">
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
.wrap{
    width: 500px;
    margin: 0 auto;
    .box{
        padding: 20px;
        margin-bottom: 20px;
        border: 1px solid #ddd;
        .title{
            margin-bottom: 15px;
            font-size: 18px;
        }
        button{
            margin: 0 10px;
        }
    }
}
</style>