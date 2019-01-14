<template>
    <div class="warning_box">
        <div class="warning_content">
            <div class="warning_top">
                <div class="warning_top_left">今日警情统计</div>
                <div class="warning_top_right"></div>
            </div>
            <div class="warning_mid">
                <div class="warning_mid_content">
                    <div class="content_box">
                        <div class="content_num">{{get_num}}</div>
                        <div class="content_title">接警</div>
                    </div>
                    <div class="content_box">
                        <div class="content_num">{{deal_num}}</div>
                        <div class="content_title">处警</div>
                    </div>
                </div>
            </div>
            <div class="warning_bottom">
                <div class="warning_bottom_top">
                    <div class="warning_radar"></div>
                    <div class="warning_marked"></div>
                </div>
                <div class="warning_bottom_grade">
                    <div class="warning_ring_box">
                        <div class="warning_ring">{{first_level_num}}</div>
                        <div class="warning_grade">1级警情</div>
                    </div>
                    <div class="warning_ring_box">
                        <div class="warning_ring second_level">{{second_level_num}}</div>
                        <div class="warning_grade">2级警情</div>
                    </div>
                    <div class="warning_ring_box">
                        <div class="warning_ring third_level">{{third_level_num}}</div>
                        <div class="warning_grade">3级警情</div>
                    </div>
                    <div class="warning_ring_box">
                        <div class="warning_ring forth_level">{{forth_level_num}}</div>
                        <div class="warning_grade">4级警情</div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import './warning.scss'
    export default {
        name: "warning",
        data(){
            return{
                get_num:3446,
                deal_num:12,
                first_level_num:5,
                second_level_num:27,
                third_level_num:52,
                forth_level_num:237
            }
        },
        methods:{
            drawRadar(){
                var echarts = require('echarts');
                var myChart = echarts.init(document.getElementsByClassName('warning_radar')[0]);
                var option = {
                    title: {
                        text: '辖区警情'
                    },
                    legend: {
                        data: ['辖区警情']
                    },
                    radar: [
                        {
                            indicator: [
                                { text: '龙华所' },
                                { text: '体育中心所' },
                                { text: '天平所' },
                                { text: '长桥所' },
                                { text: '华径所' },
                                { text: '红梅所' },
                                { text: '漕河泾所' },
                                { text: '枫林所' },
                                { text: '田林所' },
                                { text: '康建所' },
                                { text: '斜土所' },
                                { text: '凌云所' },
                                { text: '湖南所' },
                                { text: '徐家汇所' },
                                { text: '南站所' },
                            ],
                            center: ['50%', '50%'],
                            radius: 150,
                            startAngle: 90,
                            splitNumber: 8,
                            shape: 'circle',
                            name: {
                                formatter:'{value}',
                                textStyle: {
                                    color:'#000'
                                }
                            },
                            splitArea: {
                                areaStyle: {
                                    color: ['rgba(0, 0, 0, 0.4)',
                                        'rgba(0, 0, 0, 0)'],
                                    shadowColor: 'rgba(0, 0, 0, 0.4)',
                                    shadowBlur: 10
                                }
                            },
                            axisLine: {
                                lineStyle: {
                                    color: 'rgba(0, 0, 0, 0.2)'
                                }
                            },
                            splitLine: {
                                lineStyle: {
                                    color: 'rgba(255,255, 255, 1)'
                                }
                            }
                        },
                    ],
                    series: [
                        {
                            name: '',
                            type: 'radar',
                            color:'rgba(114, 172, 209, 1)',
                            itemStyle: {
                                emphasis: {
                                    // color: 各异,
                                    lineStyle: {
                                        width: 1
                                    }
                                }
                            },
                            data: [
                                {
                                    value: [0, 0.85,0.6,0,0.4,0.3,0.2,0.8,0.5,0.4,0.3,0.3,0.2,0.6,0.6],
                                    name: '',
                                    symbol: 'rect',
                                    symbolSize: 5,
                                    areaStyle:{
                                        color:'rgba(51, 173, 255, 1)'
                                    },
                                },
                            ]
                        }
                    ]
                }
                myChart.setOption(option);
            }
        },
        mounted(){
            this.drawRadar();
        }
    }
</script>

<style scoped>

</style>