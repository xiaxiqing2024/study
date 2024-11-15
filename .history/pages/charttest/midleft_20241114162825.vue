<template>
  <div ref="lineChart" style="width: 100%; height: 400px"></div>
</template>

<script>
import * as echarts from "echarts";
export default {
  mounted() {
    this.initChart();
  },
  methods: {
    initChart() {
      const chartDom = this.$refs.lineChart;
      const myChart = echarts.init(chartDom);
      const option = {
        grid: {
            left:'15%',
            bottom:30,
            right:'15%',
            top:40,
        },
        legend: {
          data: ["电费", "用电量"],
        },
        xAxis: {
          type: "category",
          boundaryGap: true,
          data: ["2020", "2021", "2022", "2023", "2024"],
        },
        yAxis: [
          {
            name: "万千瓦时",
            type: "value",
            nameTextStyle: {
              align: "left",
              fontsize: 10,
            },
            alignTicks: true,
          },
          {
            name: "万元",
            type: "value",
            nameTextStyle: {
              align: "right",
              fontsize: 10,
            },
            alignTicks: true,
          },
        ],
        series: [
          {
            name: "电费",
            type: "line",
            yAxisIndex: 0,
            data: [5100, 5200, 5400, 5000, 5800],
          },
          {
            name: "用电量",
            type: "line",
            yAxisIndex: 1,
            data: [6800, 6400, 6400, 6000, 6600],
          },
        ],
      };
      myChart.setOption(option);
    },
  },
};
</script>

<style>
</style>