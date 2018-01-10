<template>
<div class="add">
<el-button type="primary" @click="dialogFormVisible = true">新增</el-button>

<el-dialog title="政策处理" :visible.sync="dialogFormVisible">

	  <el-form ref="form" :model="form" label-width="150px">
	  <el-form-item label="政策处理费用名目">
	    <el-input v-model="form.name"></el-input>
	  </el-form-item>
	 
	  <el-form-item label="实际完成时间">
	    <el-col :span="11">
	      <el-date-picker type="date" placeholder="选择日期" v-model="form.date1" style="width: 100%;"></el-date-picker>
	    </el-col>  
	  </el-form-item>
	  <el-form-item label="发生费用">
		<el-input  v-model="input4" style="width:200px">
	    <template slot="append">万元</template>
	  </el-input>
	  </el-form-item>
	  <el-form-item label="附件">
		<el-upload
		  class="upload-demo"
		  action="https://jsonplaceholder.typicode.com/posts/"
		  :on-preview="handlePreview"
		  :on-remove="handleRemove"
		  :before-remove="beforeRemove"
		  multiple
		  :limit="3"
		  :on-exceed="handleExceed"
		  :file-list="fileList">
		  <el-button size="small" type="primary">点击上传</el-button>
		  <div slot="tip" class="el-upload__tip">只能上传jpg/png文件，且不超过500kb</div>
	    </el-upload>
	  </el-form-item>
	</el-form>

  <div slot="footer" class="dialog-footer">
    <el-button @click="dialogFormVisible = false">取 消</el-button>
    <el-button type="primary" @click="dialogFormVisible = false">确 定</el-button>
  </div>
</el-dialog>
</div>
</template>
<script>
  export default {
    data() {
      return {
      	 fileList: [],
        dialogFormVisible: false,
        form: {
          name: '',
          region: '',
          date1: '',
          date2: '',
          delivery: false,
          type: [],
          resource: '',
          desc: ''
        },
        formLabelWidth: '120px'
      };
    },
     methods: {
      handleRemove(file, fileList) {
        console.log(file, fileList);
      },
      handlePreview(file) {
        console.log(file);
      },
      handleExceed(files, fileList) {
        this.$message.warning(`当前限制选择 3 个文件，本次选择了 ${files.length} 个文件，共选择了 ${files.length + fileList.length} 个文件`);
      },
      beforeRemove(file, fileList) {
        return this.$confirm(`确定移除 ${ file.name }？`);
      }
    }
  };
</script>

<style type="text/css">
.add{
	display: block;
	float: right;
}
</style>