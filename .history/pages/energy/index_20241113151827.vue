<template>
  <div class="container">
    <!-- 饼图 -->
    <div class="chart-content">
      <div class="title">
        <v-chart
          :options="chart_name"
          style="height: 400px; width: 100%"
        ></v-chart>
      </div>
    </div>

    <!-- 表格 -->
    <div>
      <el-select
        v-model="value"
        clearable
        placeholder="请选择"
        @change="handleChange"
      >
        <el-option label="全部" value="all"></el-option>
        <el-option
          v-for="item in tableData"
          :key="item.name"
          :label="item.date"
          :value="item.date"
        ></el-option>


      </el-select>
      <i class="icon" @click="toggleSearchBox">🔍</i>
      <div v-if="showSearchBox" class="search-box">
        <el-input v-model="searchText" placeholder="请输入关键字"></el-input>
        <el-button type="primary" icon="el-icon-search" @click="handleSearch"
          >查询</el-button
        >
      </div>
    </div>

    <el-table
      :data="filteredData"
      border
      stripe
      style="width: 100%"
      :default-sort="{ prop: 'date', order: 'descending' }"
    >
      <el-table-column
        prop="date"
        label="日期"
        sortable
        width="180"
      ></el-table-column>
      <el-table-column prop="name" label="姓名" width="180"></el-table-column>
      <el-table-column
        prop="address"
        label="地址"
        :formatter="formatter"
      ></el-table-column>
    </el-table>
  </div>
</template>
  
  <script>

export default {
  name: "Energy",
  data() {
    return {
      value: "",
      searchText: "",
      showSearchBox: false,
      tableData: [
        {
          date: "2016-05-02",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1518 弄",
        },
        {
          date: "2016-05-04",
          name: "李小虎",
          address: "上海市普陀区金沙江路 1517 弄",
        },
        {
          date: "2016-05-01",
          name: "黄小虎",
          address: "上海市普陀区金沙江路 1519 弄",
        },
        {
          date: "2016-05-03",
          name: "大小虎",
          address: "上海市普陀区金沙江路 1516 弄",
        },
      ],
      filteredData: [],
      chart_name: {
        title: {
          text: "姓名分布",
          subtext: "基于表格数据",
          left: "center",
        },
        tooltip: {
          trigger: "item",
        },
        legend: {
          orient: "vertical",
          left: "left",
        },
        series: [
          {
            name: "姓名",
            type: "pie",
            radius: "50%",
            data: [], // 初始化为空
            emphasis: {
              itemStyle: {
                shadowBlur: 10,
                shadowOffsetX: 0,
                shadowColor: "rgba(0, 0, 0, 0.5)",
              },
            },
          },
        ],
      },
    };
  },
  methods: {
    formatter(row, _column) {
      return row.address;
    },
    handleChange(selectedValue) {
      console.log("选中的:", selectedValue);
      if (!selectedValue) {
        this.filteredData = this.tableData;
      } else if (selectedValue === "all") {
        this.filteredData = this.tableData;
      } else {
        this.filteredData = this.tableData.filter(
          (item) => item.date === selectedValue
        );
      }
      this.updateChartData(); // 更新图表数据
    },
    toggleSearchBox() {
      this.showSearchBox = !this.showSearchBox;
      if (!this.showSearchBox) {
        this.resetSearch();
      }
    },
    resetSearch() {
      this.searchText = ""; // 清空搜索框
      this.filteredData = this.tableData; // 重新显示所有数据
      this.updateChartData(); // 更新图表数据
    },
    handleSearch() {
      console.log("搜索按钮被点击");
      const searchText = this.searchText.trim();
      if (!searchText) {
        this.filteredData = this.tableData;
      } else {
        this.filteredData = this.tableData.filter((item) => {
          return Object.values(item).some((value) =>
            String(value).includes(searchText)
          );
        });
      }
      this.updateChartData(); // 更新图表数据
    },
    updateChartData() {
      // 根据 filteredData 更新图表数据
      const nameCounts = {};
      this.filteredData.forEach((item) => {
        nameCounts[item.name] = (nameCounts[item.name] || 0) + 1; // 统计姓名出现次数
      });

      // 将统计结果转换为饼图数据格式
      const chartData = Object.entries(nameCounts).map(([name, count]) => ({
        name,
        value: count,
      }));
      console.log(chartData); // 调试输出
      this.chart_name.series[0].data = chartData; // 更新饼图数据
    },
  },
  mounted() {
    this.filteredData = this.tableData;
    this.updateChartData(); // 初始化图表数据
  },
};
</script>
  
  <style scoped>
  .container{
    background-color: rgba(0,0,0,0.4);
  }
.search-box {
  margin-top: 10px;
}
</style>