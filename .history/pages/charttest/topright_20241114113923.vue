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
        legend: {
          data: ["Search Engine", 'Direct',"Direct(Traffic Sources)", "Marketing", "Baidu", "Email"],
        },
        series: [
          {
            name: "Marketing Channels",
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
              { value: 1548, name: "Search Engine",labelLine: { show: false }},
              { value: 775, name: "Direct",labelLine: { show: false }},
              { value: 679, name: "Marketing" },
            ],
          },
          {
            name: "Traffic Sources", // 添加名称以匹配图例
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
            },
            data: [
              { value: 1048, name: "Baidu" ,labelLine: { show: false }},
              { value: 335, name: "Direct(Traffic Sources)" },
              { value: 310, name: "Email" ,labelLine: { show: false }},
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