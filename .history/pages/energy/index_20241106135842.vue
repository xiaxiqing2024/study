<template>
  <div>
    <div>
      <el-select v-model="value" placeholder="请选择" @change="handleChange">
        <el-option
          v-for="item in tableData"
          :key="item.name"
          :label="item.date"
          :value="item.date"
        >
        </el-option>
      </el-select>
      <i class="icon" @click="toggleSearchBox">111</i>
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
      <el-table-column prop="date" label="日期" sortable width="180">
      </el-table-column>
      <el-table-column prop="name" label="姓名" width="180"> </el-table-column>
      <el-table-column prop="address" label="地址" :formatter="formatter">
      </el-table-column>
    </el-table>
  </div>
</template>
  
  <script>
export default {
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
    };
  },
  methods: {
    formatter(row, column) {
      return row.address;
    },
    handleChange(selectedValue) {
      console.log("选中的:", selectedValue);
      if (!selectedValue) {
        this.filteredData = this.tableData;
        return;
      }
      this.filteredData = this.tableData.filter(
        (item) => item.date === selectedValue
      );
      
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
    },
    handleSearch() {
      console.log("搜索按钮被点击"); // 添加这一行
      const searchText = this.searchText.trim();
      if (!searchText) {
        this.filteredData = this.tableData;
        return;
      }
      this.filteredData = this.tableData.filter((item) => {
        return Object.values(item).some((value) => {
          return String(value).includes(searchText);
        });
      });
    },
  },
  mounted() {
    this.filteredData = this.tableData;
  },
};
</script>