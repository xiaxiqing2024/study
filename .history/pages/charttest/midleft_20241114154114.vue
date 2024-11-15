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

            };
            myChart.setOption(option);

        },

    },

}
</script>

<style>

</style>