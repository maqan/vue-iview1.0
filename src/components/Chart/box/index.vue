<template>
    <Row>
        <Col span="12">
            <div id="chart1" :style="{width: '100%', height: '450px'}"></div>
        </Col>
        <Col span="12">
            <div id="chart2" :style="{width: '100%', height: '450px'}"></div>
        </Col>
    </Row>
</template>
<script>
    export default {
        mounted() {
            this.$nextTick(() => {
                this.chartLine1();
                this.chartLine2();
            });
        },
        methods: {
            chartLine1() {

                // 绘制图表
                let option = {
                    title: {text: "在Vue中使用echarts1"},
                    tooltip: {},
                    xAxis: {
                        data: ["衬衫", "羊毛衫", "雪纺衫", "裤子", "高跟鞋", "袜子"]
                    },
                    yAxis: {},
                    series: [
                        {
                            name: "销量",
                            type: "bar",
                            data: [5, 20, 36, 10, 10, 20]
                        }
                    ]
                };
                // 基于准备好的dom，初始化echarts实例
                let myCharts1 = this.$echarts.init(document.getElementById("chart1"));
                myCharts1.setOption(option);
            },
            chartLine2() {


                let option = {
                    title: {text: "在Vue中使用echarts2"},
                    color: ["#f44"],
                    tooltip: {
                        trigger: "axis",
                        axisPointer: {
                            type: "shadow"
                        }
                    },
                    xAxis: {
                        type: "category",
                        data: [
                            "1月",
                            "2月",
                            "3月",
                            "4月",
                            "5月",
                            "6月",
                            "7月",
                            "8月",
                            "9月",
                            "10月",
                            "11月",
                            "12月"
                        ]
                    },
                    yAxis: {},
                    series: [
                        {
                            name: "每月花费",
                            type: "bar",
                            barWidth: "60%",
                            data: [995, 666, 444, 858, 654, 236, 645, 546, 846, 225, 547, 356]
                        }
                    ]
                };
                let myCharts2 = this.$echarts.init(document.getElementById("chart2"));
                myCharts2.setOption(option);
            }
        }
    };
</script>