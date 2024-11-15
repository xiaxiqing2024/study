<template>
  <div ref="TopRightChart" style="width: 100%; height: 400px"></div>
</template>

<script>
import * as echarts from "echarts";
export default {
  mounted() {
    this.initChart();
  },
  methods: {
    initChart() {
      const chartDom = this.$refs.TopRightChart;
      const myChart = echarts.init(chartDom);
      const option = {
        color: ["#f48f5e", "#57a9fa", "#38e2ec"], // 定义颜色数组
        legend: {
          data: [
            "Search Engine",
            "Direct",
            "Direct(Traffic Sources)",
            "Marketing",
            "Baidu",
            "Email",
          ],
        },
        series: [
          {
            type: "pie",
            radius: ["33%", "50%"],
            center: ["50%", "55%"],
            colorBy: "series",
            label: {
              show: true,
              formatter() {
                return "测试";
              },
              fontSize: 14,
            },
            labelLine: {
              length: 20,
            },
            data: [1],
          },
          {
            type: "pie",
            radius: ["33%", "50%"],
            center: ["50%", "55%"],
            label: { show: false },
            data: [
              {
                value: 1548,
                name: "Search Engine",
              },
              { value: 775, name: "Direct" },
              { value: 679, name: "Marketing" },
            ],
          },
          {
            type: "pie",
            radius: ["68%", "85%"],
            center: ["50%", "55%"],
            colorBy: "series",
            label: {
              show: true,
              fontSize: 14,
              formatter() {
                return "测试2";
              },
              labelLine: {
                length: 20,
              },
              position: "left",
            },
            data: [1],
          },
          {
            type: "pie",
            radius: ["68%", "85%"],
            center: ["50%", "55%"],
            label: { show: false },
            data: [
              {
                value: 1048,
                name: "Baidu",
              },
              { value: 335, name: "Direct(Traffic Sources)" },
              { value: 310, name: "Email" },
            ],
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