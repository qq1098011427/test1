<template>
 <div id="main">
  <div class="btnsum">
  <el-input style="width:250px" size="large" v-model="input" placeholder="输入政策处理费用名目"></el-input>
    <el-select v-model="value" placeholder="审核状态" style="width:110px;">
    <el-option
      v-for="item in options"
      :key="item.value"
      :label="item.label"
      :value="item.value">
    </el-option>
    </el-select>
    <el-button type="primary">搜索</el-button>
    <el-badge :value="8" :max="10" style="margin-left:10px">
    <el-button size="small" style="color:green;background-color:#e4e4e4">审核通过</el-button>
    </el-badge>

    <v-dialog></v-dialog>

  </div>

  <el-table
  :data="tableData"
  height="330"
  border
  style="width: 100%">
  <el-table-column 
    fixed
    prop="date"
    label="序号"
    width="80"
    header-align="center"
    align="center">
  </el-table-column>
  <el-table-column
    prop="name"
    label="政策处理费用名目"
    width="540">
  </el-table-column>
  <el-table-column
    prop="province"
    label="实际完成时间"
    width="170"
    header-align="center"
    align="center"
    >
  </el-table-column>
  <el-table-column
    prop="money"
    label="发生费用(万元)"
    width="170"
    header-align="right"
    align="right">
  </el-table-column>
   <el-table-column       
    label="审核状态"
    width="100">

  <template slot-scope="scope">
  <el-button
    size="mini"
    type="warning">删除</el-button>
  </template>
   </el-table-column>
   <el-table-column
    label="操作"
    >
    <template slot-scope="scope">
    <el-dropdown>
    <span class="el-dropdown-link">
      操作<i class="el-icon-arrow-down el-icon--right"></i>
    </span>
    <el-dropdown-menu slot="dropdown">
      <el-dropdown-item>查看</el-dropdown-item>
      <el-dropdown-item>编辑</el-dropdown-item>
      <el-dropdown-item>删除</el-dropdown-item>
      <el-dropdown-item>上报</el-dropdown-item>
    </el-dropdown-menu>
    </el-dropdown>
    </template>
    </el-table-column>
    </el-table>
    
      <div class="block">
      <span class="demonstration"></span>
      <el-pagination
        @size-change="handleSizeChange"
        @current-change="handleCurrentChange"
        :current-page="currentPage4"
        :page-sizes="[5, 10, 20]"
        :page-size="5"
        layout="total, sizes, prev, pager, next, jumper"
        :total="20">
      </el-pagination>
    </div>
  </div>
</template>

<script>
import dialog from './dialog'
  export default{
    name:'app',
      data(){
        return{
        options:[{
          value:'选项1',
          label: '审核通过'
        },{
          value: '选项2',
          label: '未通过'
        }],
        tableData:[{
          date: '1',
          name: '政策处理进度款',
          province: '2017-03-07',
          money: 200333
        },{
          date: '2',
          name: '政策处理进度款',
          province: '2017-03-07',
          money: 200333
        },
        {
          date: '3',
          name: '5月份政策处理完成投资',
          province: '2017-03-07',
          money: 200333
        }, {
          date: '4',
          name: '5月份政策处理完成投资',
          province: '2017-03-07',
          money: 200333
        },
         {
          date: '5',
          name: '5月份政策处理完成投资',
          province: '2017-03-07',
          money: 200333
        },
         {
          date: '6',
          name: '5月份政策处理完成投资',
          province: '2017-03-07',
          money: 200333
        },
         {
          date: '7',
          name: '5月份政策处理完成投资',
          province: '2017-03-07',
          money: 200333
        },
         {
          date: '8',
          name: '5月份政策处理完成投资',
          province: '2017-03-07',
          money: 200333
        }],
        
        currentPage1: 5,
        currentPage2: 5,
        currentPage3: 5,
        currentPage4: 4
        
      }
    }, methods: {
      handleSizeChange(val) {
        console.log(`每页 ${val} 条`);
      },
      handleCurrentChange(val) {
        console.log(`当前页: ${val}`);
      }
    },
    components:{
      'v-dialog':dialog
    }
  }
</script>
<style scoped>
#main{
  display: block;
  margin:12px 70px;
  padding-bottom: 5px;
  border-top:1px solid #aaaaaa;
  border-bottom:1px solid #aaaaaa;
  box-shadow:0 -1.5px 0 #e1e1e1;
}
.btnsum{
  margin:10px 0 15px 12px;
}
.block{
  margin-left:680px; 
}
.el-table{
  margin-bottom: 10px;
  font-family: "PingFang SC";
  color: #606266;
}
</style>