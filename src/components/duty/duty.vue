<template>
    <div class="duty-container">
        <div class="duty-top">
            <div class="duty-top-left">值班备勤</div>
            <div class="duty-top-right"></div>
        </div>
        <div class="duty-bottom">
            <div class="duty-central">【徐汇分局】</div>
            <div class="duty-central-info">
                <div class="info-grade">三级勤务</div>
                <div class="info-detail">
                    <div class="central-leader">分局领导: <span>{{leader}}</span></div>
                    <ul class="central-personnal">
                        <li class="central-personnal-left">指挥长: <span>{{zhz}}</span> </li>
                        <li class="central-personnal-right">总值班：<span>{{zzb}}</span></li>
                        <li class="central-personnal-left">交警指挥长：<span>{{jjzhz}}</span> </li>
                        <li class="central-personnal-right">副值班：<span>{{fzb}}</span> </li>
                    </ul>
                </div>
            </div>
            <div class="duty-bottom-swiper">
                <swiper :options="swiperOption" ref="mySwiper">
                    <!-- slides -->
                    <swiper-slide v-for="slide in swiperSlides" :key="slide.id" >
                        <div class="sub-bureau-name">【{{slide.name}}】</div>
                        <ul class="sub-bureau-info">
                            <li>总值班：<span>{{slide.zong_zhi_ban}}</span> </li>
                            <li>副值班：<span>{{slide.fu_zhi_ban}}</span> </li>
                            <li>指挥长：<span>{{slide.zhi_hui_zhang}}</span> </li>
                            <li>交警指挥长：<span>{{slide.jiao_jing}}</span></li>
                        </ul>
                    </swiper-slide>
                    <!--<swiper-slide>I'm Slide 2</swiper-slide>-->
                    <!--<swiper-slide>I'm Slide 3</swiper-slide>-->
                    <!--<swiper-slide>I'm Slide 4</swiper-slide>-->
                    <!--<swiper-slide>I'm Slide 5</swiper-slide>-->
                    <!--<swiper-slide>I'm Slide 6</swiper-slide>-->
                    <!--<swiper-slide>I'm Slide 7</swiper-slide>-->
                    <!-- Optional controls -->
                    <div class="swiper-button-prev" slot="button-prev"></div>
                    <div class="swiper-button-next" slot="button-next"></div>
                </swiper>

            </div>
        </div>
    </div>
</template>

<script>
    import './duty.scss'
    import  { swiper,swiperSlide } from 'vue-awesome-swiper'
    export default {
        name: "duty",
        data(){
            return{
                leader:'高鹏鹏',
                zhz:'小东',
                zzb:'小西',
                jjzhz:'小南',
                fzb:'小北',
                swiperOption: {
                    // some swiper options/callbacks
                    // 所有的参数同 swiper 官方 api 参数
                    // ...
                    slidesPerView: 2,
                    autoplay:true,
                    loop:true,
                    navigation: {
                        nextEl: '.swiper-button-next',
                        prevEl: '.swiper-button-prev'
                    }
                },
                swiperSlides:[
                    {id:0,name:'宜山所',zong_zhi_ban:'小东',fu_zhi_ban:'小西',zhi_hui_zhang:'小南',jiao_jing:'小北'},
                    {id:1,name:'龙华所',zong_zhi_ban:'小上',fu_zhi_ban:'小下',zhi_hui_zhang:'小左',jiao_jing:'小右'},
                    {id:2,name:'天平所',zong_zhi_ban:'小东',fu_zhi_ban:'小西',zhi_hui_zhang:'小南',jiao_jing:'小北'},
                    {id:3,name:'长桥所',zong_zhi_ban:'小上',fu_zhi_ban:'小下',zhi_hui_zhang:'小左',jiao_jing:'小右'},
                    {id:4,name:'红梅所',zong_zhi_ban:'小东',fu_zhi_ban:'小西',zhi_hui_zhang:'小南',jiao_jing:'小北'},
                    {id:5,name:'田林所',zong_zhi_ban:'小上',fu_zhi_ban:'小下',zhi_hui_zhang:'小左',jiao_jing:'小右'},
                    {id:6,name:'斜土所',zong_zhi_ban:'小东',fu_zhi_ban:'小西',zhi_hui_zhang:'小南',jiao_jing:'小北'},
                    {id:7,name:'湖南所',zong_zhi_ban:'小上',fu_zhi_ban:'小下',zhi_hui_zhang:'小左',jiao_jing:'小右'},
                ]
            }
        },
        components: {
            swiper,
            swiperSlide
        },
        computed: {
            swiper() {
                return this.$refs.mySwiper.swiper
            }
        },
        methods:{

        }
    }
</script>

<style lang="scss" scoped>

</style>