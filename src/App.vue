<!--
 * @Author: error: git config user.name && git config user.email & please set dead value or install git
 * @Date: 2022-08-30 11:23:47
 * @LastEditors: error: git config user.name && git config user.email & please set dead value or install git
 * @LastEditTime: 2022-08-30 16:13:10
 * @FilePath: \vue3-demo\src\App.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->


<template>
    <div class="table-box">
      <!-- 标题 -->
      <div class="title">
        <h2>curd</h2>
        <div class="query">
          <el-input v-model="queryInput" placeholder="请输入姓名搜索" />
          <el-button type="primary">增加</el-button>
        </div>
        <!-- table -->
        <el-table
          ref="multipleTableRef"
          :data="tableData"
          style="width: 100%"
          @selection-change="handleSelectionChange"
        >
          <el-table-column type="selection" width="55" />
          <el-table-column label="Date" width="120">
            <template #default="scope">{{ scope.row.date }}</template>
          </el-table-column>
          <el-table-column property="name" label="Name" width="120" />
          <el-table-column property="address" label="Address" show-overflow-tooltip />
        </el-table>
        <div style="margin-top: 20px">
          <el-button @click="toggleSelection()">Clear selection</el-button>
        </div>
      </div>
    </div>
</template>

<script setup>
import { ref } from "vue";
    // 数据
    let queryInput = ref("")
    let tableData=ref([
        {
        date: '2016-05-03',
        name: 'Tom',
        address: 'No. 189, Grove St, Los Angeles',
      },
      {
        date: '2016-05-02',
        name: 'Tom',
        address: 'No. 189, Grove St, Los Angeles',
      },
      {
        date: '2016-05-04',
        name: 'Tom',
        address: 'No. 189, Grove St, Los Angeles',
      },
      {
        date: '2016-05-01',
        name: 'Tom',
        address: 'No. 189, Grove St, Los Angeles',
      },
      {
        date: '2016-05-08',
        name: 'Tom',
        address: 'No. 189, Grove St, Los Angeles',
      },
      {
        date: '2016-05-06',
        name: 'Tom',
        address: 'No. 189, Grove St, Los Angeles',
      },
      {
        date: '2016-05-07',
        name: 'Tom',
        address: 'No. 189, Grove St, Los Angeles',
      },
    ])
    // 方法
      const toggleSelection=()=>{
        console.log('click')
      }
</script>

<style scoped>
.table-box{
  width:800px;
  position: absolute;
  top:50%;
  left:50%;
  transform: translate(-50%, -50%);
}
</style>
