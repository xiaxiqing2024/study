<template>
  <div ref="lineChart"></div>
</template>

<script>
import * as echarts from "echarts";
export default {
    mounted(){
        this.initChart();

    },
    methods:{
        initChart(){
            const chartDom = this.$refs.lineChart;
            const myChart = echarts.init(chartDom);
            const option = {
                legend:{
                    data:['用电量','电费']
                },
                xAxis:{
                    type:'category',
                    boundaryGap:true,
                    data:['2020','2021','2022','2023','2024']

                },
                yAxis:{
                    type:'value'
                },
                series:[
                    {
                        type:'line',
                        stack:'Total',
                        data:[5100,5200,5400,5000,5800]
                    },
                    {
                        type:'line',
                        stack:'Total',
                        data:[6800,6400,6400,6000,6600]
                    },
                ]

            };
            myChart.setOption(option);

        },

    },

}
</script>

<style>

</style>