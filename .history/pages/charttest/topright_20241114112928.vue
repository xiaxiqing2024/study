<template>
  <div ref="TopRightChart"></div>
</template>

<script>
import * as echarts from 'echarts';
export default {
  mounted() {
    this.initChart();
  },
  methods: {
    initChart() {
      const chartDom = this.$refs.TopRightChart;
      const myChart = echarts.init(chartDom);
      const option = {
        legend: {
          data: ["a", "b", "c"],
        },
        series: [
          {
            type: "pie",
            radius: ["33%", "50%"],
            center: ["50%", "55%"],
            label: {
              show: true,
              formatter() {
                return "ccc";
              },
              fontSize: 14,
            },
            labelLine: {
              length: 20,
            },
            data: [
              { value: 1548, name: "Search Engine" },
              { value: 775, name: "Direct" },
              { value: 679, name: "Marketing" },
            ],
          },
          {
            type: "pie",
            radius: ["68%", "85%"],
            center: ["50%", "55%"],
            label: {
              show: true,
              fontSize: 14,
              formatter() {
                return "MMM";
              },
              labelLine: {
                length: 20,
              },
              data: [
                { value: 1048, name: "Baidu" },
                { value: 335, name: "Direct" },
                { value: 310, name: "Email" },
              ],
            },
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