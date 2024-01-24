<template>
  <div style="padding: 10px;width: 100%">
    <div style="padding: 10px">
      <el-button type="primary">Add</el-button>
      <el-button type="primary">Import</el-button>
      <el-button type="primary">Export</el-button>
    </div>

    <div style="margin: 10px 0">
      <el-input v-model="search" placeholder="Please input" style="width: 50%"/>
      <el-button style="margin: 5px" type="primary">Search</el-button>
    </div>
    <el-table :data="tableData" stripe border style="width: 100%">
      <el-table-column prop="date" label="Date" sortable/>
      <el-table-column prop="name" label="Name" />
      <el-table-column prop="address" label="Address" />
      <el-table-column fixed="right" label="Operations" width="120">
        <template #default>
          <el-button link type="primary" @click="handleEdit"
          >Edit</el-button
          >
          <el-popconfirm title="Are you sure to delete this?">
            <template #reference>
              <el-button link type="primary">Delete</el-button>
            </template>
          </el-popconfirm>
        </template>
      </el-table-column>
    </el-table>
    <div class="demo-pagination-block" style="padding: 10px">
      <div class="demonstration"></div>
      <el-pagination
          v-model:current-page="currentPage"
          v-model:page-size="pageSize"
          :page-sizes="[5, 10, 20]"
          layout="total, sizes, prev, pager, next, jumper"
          :total="total"
          @size-change="handleSizeChange"
          @current-change="handleCurrentChange"
      />
    </div>
  </div>



</template>

<script>
// @ is an alias to /src
export default {
  name: 'HomeView',
  components: {
  },
  data(){
    return{
      search:"",
      currentPage:1,
      pageSize:5,
      total:20,
      tableData: [
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
        }
      ]
    }
  },methods:{
    handleEdit(){

    },
    handleSizeChange(){

    },
    handleCurrentChange(){

    }

  }
}
</script>
