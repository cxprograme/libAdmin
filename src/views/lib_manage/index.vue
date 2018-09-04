<template>
  <el-container>
    <el-header style="height:auto;overflow:hidden;">
      <el-row :gutter="12">
        <el-col :span="8">
          <el-card shadow="always">
          	<div class="layout_container">
	           	<span class="icon_container">
	           		<i class="el-icon-tickets normal"></i>
	           	</span>
	           	<div class="info">
	           		<span class="num">773232</span>
	           		<span>图书总量</span>
	           	</div>
	         </div>
			</el-card>
        </el-col>
        <el-col :span="8">
          <el-card shadow="always">
            <div class="layout_container">
	           	<span class="icon_container">
	           		<i class="el-icon-tickets normal"></i>
	           	</span>
	           	<div class="info">
	           		<span class="num">773232</span>
	           		<span>图书总量</span>
	           	</div>
	         </div>
          </el-card>
        </el-col>
        <el-col :span="8">
          <el-card shadow="always">
            <div class="layout_container">
	           	<span class="icon_container">
	           		<i class="el-icon-tickets normal"></i>
	           	</span>
	           	<div class="info">
	           		<span class="num">773232</span>
	           		<span>图书总量</span>
	           	</div>
	         </div>
          </el-card>
        </el-col>
      </el-row>
    </el-header>
    <el-main>
    	<el-row style="background-color:rgb(223,223,223);padding:20px">
    		<span>
    			<i class="el-icon-tickets"></i>
    		</span>
    		<span>图书管理</span>
    	</el-row>
    	<el-row>
	    	<el-form :inline="true" :model="form" class="demo-form-inline" style="text-align:center;padding:20px">
			  <el-form-item label="审批人">
			    <el-input v-model="form.user" placeholder="审批人"></el-input>
			  </el-form-item>
			  <el-form-item label="活动区域">
			    <el-select v-model="form.region" placeholder="活动区域">
			      <el-option label="区域一" value="shanghai"></el-option>
			      <el-option label="区域二" value="beijing"></el-option>
			    </el-select>
			  </el-form-item>
			  <el-form-item label="活动区域">
			   	<el-select v-model="value" placeholder="请选择">
				    <el-option
				      v-for="item in options"
				      :key="item.value"
				      :label="item.label"
				      :value="item.value">
				    </el-option>
			  	</el-select>
			  </el-form-item>
			  <el-form-item>
			    <el-button type="primary" @click="onSubmit">查询</el-button>
			  </el-form-item>
			</el-form>
		</el-row>
		<el-container>
	  		<el-header class='book_header'>
	  			<el-row>
	  				<el-col :span='12'>
		  			<span>
		    			<i class="el-icon-tickets"></i>
		    		</span>
		    		<span>图书管理</span>
					</el-col>
					<el-col :span='12' style="text-align:right">
						<el-button type="primary" @click="dialogFormVisible = true">添加图书</el-button>
						<el-button type="primary">修改图书</el-button>
						<el-button type="primary">下架</el-button>
					</el-col>
				</el-row>
	  		</el-header>
	  		<el-container class="book_main">
	    		<el-aside style="overflow-y:scroll;width:400px">
	    			<el-collapse v-model="activeNames" @change="handleChange">
						  <el-collapse-item title="ID:2341-互联网思维" name="1">
						    <ul>
						    	<li><span>编号:HS23232</span><span>架上</span></li>
						    	<li><span>编号:HS23232</span><span>架上</span></li>
						    	<li><span>编号:HS23232</span><span>架上</span></li>
						    	<li><span>编号:HS23232</span><span>架上</span></li>
						    </ul>
						  </el-collapse-item>
						  <el-collapse-item title="ID:2341-互联网思维" name="2">
						    <ul>
						    	<li><span>编号:HS23232</span><span>架上</span></li>
						    	<li><span>编号:HS23232</span><span>架上</span></li>
						    	<li><span>编号:HS23232</span><span>架上</span></li>
						    	<li><span>编号:HS23232</span><span>架上</span></li>
						    </ul>
						  </el-collapse-item>
						  <el-collapse-item title="ID:2341-互联网思维" name="3">
						    	<li><span>编号:HS23232</span><span>架上</span></li>
						    	<li><span>编号:HS23232</span><span>架上</span></li>
						    	<li><span>编号:HS23232</span><span>架上</span></li>
						    	<li><span>编号:HS23232</span><span>架上</span></li>
						  </el-collapse-item>
						  <el-collapse-item title="ID:2341-互联网思维" name="4">
						    	<li><span>编号:HS23232</span><span>架上</span></li>
						    	<li><span>编号:HS23232</span><span>架上</span></li>
						    	<li><span>编号:HS23232</span><span>架上</span></li>
						    	<li><span>编号:HS23232</span><span>架上</span></li>
						  </el-collapse-item>
						</el-collapse>
	    		</el-aside>
	    		<el-main>
	    			<el-row :gutter='20'>
	    				<el-col :span='6'>
	    					<div style="width:120px;height:120px;background-color:red;"></div>
	    				</el-col>
	    				<el-col :span='18' >
	    					<el-row style="padding:10px 0;">
	    						<el-col :span='10' style='text-align:left;'>
	    							<span>互联网思维</span>
	    						</el-col>
	    						<el-col :span='2' :offset="12">
	    							<span>9.3分</span>
	    						</el-col>
	    					</el-row>
	    					<el-row style='text-align:left;padding:10px 0;'>独孤九剑</el-row>
	    					<el-row style='text-align:left;padding:10px 0;'>独孤九剑受伤的受伤的都是是大多数都是</el-row>
	    				</el-col>
	    			</el-row>
	    			<el-row style="margin-top:20px">
		    			<el-tabs type="border-card" stretch='true'>
						  <el-tab-pane label="评论" style="height:200px;overflow-y:scroll">
						    <el-row style="border:1px solid #eee;padding:10px">
						    	<el-row>
							    	<el-col :span='2' >
							    		<el-row>
							    			<div style="width:50px;height:50px;background-color:red">图片</div>
							    		</el-row>
							    	</el-col>
							    	<el-col :span='20' :offset='1' >
							    		<el-row>
							    			<el-col :span='4' style="text-align:left;">咱小潘</el-col>
							    			<el-col :span="4" :offset="16"><span>最佳推荐</span></el-col>
							    		</el-row>
							    		<el-col style="text-align:left;padding:10px 0 0 0">1月30 12:30</el-col>
							    		
							    	</el-col>
							    </el-row>
							    <el-row style="padding:10px 0 0 0">
							    	<el-col :span='2'>9.3分</el-col>
							    	<el-col :span="21" :offset='1' style="text-align:left">这本数太赞了,值得一看</el-col>
						    	</el-row>
						    </el-row>
						    <el-row style="border:1px solid #eee;padding:10px">
						    	<el-row>
							    	<el-col :span='2' >
							    		<el-row>
							    			<div style="width:50px;height:50px;background-color:red">图片</div>
							    		</el-row>
							    	</el-col>
							    	<el-col :span='20' :offset='1' >
							    		<el-row>
							    			<el-col :span='4' style="text-align:left;">咱小潘</el-col>
							    			<el-col :span="4" :offset="16"><span>最佳推荐</span></el-col>
							    		</el-row>
							    		<el-col style="text-align:left;padding:10px 0 0 0">1月30 12:30</el-col>
							    		
							    	</el-col>
							    </el-row>
							    <el-row style="padding:10px 0 0 0">
							    	<el-col :span='2'>9.3分</el-col>
							    	<el-col :span="21" :offset='1' style="text-align:left">这本数太赞了,值得一看</el-col>
						    	</el-row>
						    </el-row>
						    <el-row style="border:1px solid #eee;padding:10px">
						    	<el-row>
							    	<el-col :span='2' >
							    		<el-row>
							    			<div style="width:50px;height:50px;background-color:red">图片</div>
							    		</el-row>
							    	</el-col>
							    	<el-col :span='20' :offset='1' >
							    		<el-row>
							    			<el-col :span='4' style="text-align:left;">咱小潘</el-col>
							    			<el-col :span="4" :offset="16"><span>最佳推荐</span></el-col>
							    		</el-row>
							    		<el-col style="text-align:left;padding:10px 0 0 0">1月30 12:30</el-col>
							    		
							    	</el-col>
							    </el-row>
							    <el-row style="padding:10px 0 0 0">
							    	<el-col :span='2'>9.3分</el-col>
							    	<el-col :span="21" :offset='1' style="text-align:left">这本数太赞了,值得一看</el-col>
						    	</el-row>
						    </el-row>
						  </el-tab-pane>
						  <el-tab-pane label="消息中心">消息中心</el-tab-pane>
						</el-tabs>
					</el-row>
	    		</el-main>
	  		</el-container>
		</el-container>
	</el-main>
	<el-dialog title="添加图书" :visible.sync="dialogFormVisible" >
	  <el-form  size="mini"  label-width="80px" :model="bookform" style="padding:0 10px">
	     	<el-form-item label="书名">
	    		<el-input v-model="bookform.book_name"></el-input>
	  		</el-form-item>
		    <el-form-item label="作者">
	    		<el-input v-model="bookform.author"></el-input>
	  		</el-form-item>
	  		<el-form-item label="上架时间">
	    		<el-date-picker
			      v-model="bookform.update_time"
			      type="datetime"
			      placeholder="选择日期时间">
			    </el-date-picker>
	  		</el-form-item>
	  		<el-form-item label="推荐">
			    <el-checkbox-group v-model="bookform.type">
			      <el-checkbox label="首页" name="type"></el-checkbox>
			      <el-checkbox label="图书借阅" name="type"></el-checkbox>
			    </el-checkbox-group>
			</el-form-item>
			<el-form-item
			    v-for="(book, index) in bookform.booknos"
			    :label="'图书编号'"
			    :key="book.key"
			    :rules="{
			      required: true, message: '图书编号不能为空', trigger: 'blur'
			    }"
			  >
			  	<el-col :span='11'>
			    	<el-input v-model="book.value"></el-input>
				</el-col>
				<el-col :span='11' :offset='2'>
					<el-button @click.prevent="removeBookNo(book)">删除</el-button>
				</el-col>
  			</el-form-item>
  			<el-form-item>
			    <el-button @click="addBookNo" type='primary' style="width:46%">继续添加</el-button>
			 </el-form-item>
			 <el-form-item label="封面图片">
				 <el-upload
				  class="avatar-uploader"
				  :action='importUrl'
				  name='picture'
				  :show-file-list="false"
				  :on-success="handleAvatarSuccess"
				  :before-upload="beforeAvatarUpload">
				  <img v-if="imageUrl" :src="imageUrl" class="avatar">
				  <i v-else class="el-icon-plus avatar-uploader-icon"></i>
				</el-upload>
			</el-form-item>
			<el-form-item label="图书简介">
            <div class="edit_container">
              <quill-editor v-model="bookform.describe"
                            ref="myQuillEditor"
                            class="editer"
                            :options="editorOption" @ready="onEditorReady($event)">
              </quill-editor>
            </div>
          </el-form-item>
		</el-form>
		<div slot="footer" class="dialog-footer">
		    <el-button @click="dialogFormVisible = false">取 消</el-button>
		    <el-button type="primary" @click="submit">确 定</el-button>
		</div>
	</el-dialog>
</el-container>

</template>

<script>
import { quillEditor } from 'vue-quill-editor' //调用编辑器
export default {
  data() {
    return {
      value:'',
      dialogFormVisible:false,
      importUrl:'http://localhost:8081/menuwork/hs/back/lib/upload',
      bookform:{
      	book_name:'',
      	author:'',
      	update_time:'',
      	type:'',
      	booknos:[{
      		value:''
      	}],
      	describe:''
      },
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
       options: [{
          value: '选项1',
          label: '黄金糕'
        }, {
          value: '选项2',
          label: '双皮奶'
        }, {
          value: '选项3',
          label: '蚵仔煎'
        }, {
          value: '选项4',
          label: '龙须面'
        }, {
          value: '选项5',
          label: '北京烤鸭'
        }],
        activeNames: ['1'],
        stretch:true,
        activeName2: 'first'
    }
  },
    components: {
//使用编辑器
      quillEditor
    },
  methods: {
  	handleAvatarSuccess(res, file) {
        this.imageUrl = URL.createObjectURL(file.raw);
	  },
	  beforeAvatarUpload(file) {
	    const isJPG = file.type === 'image/jpeg';
	    const isLt2M = file.size / 1024 / 1024 < 2;
	    console.log(file);
	    if (!isJPG) {
	      this.$message.error('上传头像图片只能是 JPG 格式!');
	    }
	    if (!isLt2M) {
	      this.$message.error('上传头像图片大小不能超过 2MB!');
	    }
	    return isJPG && isLt2M;
	  },
    onSubmit() {
      this.$message('submit!')
    },
    onCancel() {
      this.$message({
        message: 'cancel!',
        type: 'warning'
      })
    },
    handleChange(){

    },
    /**
     * 图书添加信息
     * @return {[type]} [description]
     */
    submit:function(){
    	console.log(this.bookform);
    },
    removeBookNo(item) {
        var index = this.bookform.booknos.indexOf(item)
        if (index !== -1) {
          this.bookform.booknos.splice(index, 1)
        }
	  },
	  addBookNo() {
	    this.bookform.booknos.push({
	      value: '',
	      key: Date.now()
	    });
	  }
  }
}
</script>

<style scoped>
	.layout_container{
		display: flex;
		flex-direction: row;
	}
	.icon_container{
		display: inline-block;
		width:80px;
		height:80px;
		border-radius:50%;
		background-color:red;
		text-align: center;
	}
	.normal{
		line-height: 80px;
		color:#fff;
		font-size:25px;

	}
	.info{
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items:center;
	}
	.info span{

		display: flex;
		justify-content: center;
		padding-left: 50px;
		padding-top: 10px
	}
	.info span.num{
		font-size: 25px;
		font-weight: bold;
	}
	
	.book_header{
	    color: #333;
	    line-height: 60px;
	  }
	  
	  .el-aside {
	    color: #333;
	    text-align: center;
	    line-height: 200px;
	    width: 500px;
	    height: 450px;
	  }
	  
	  .book_main{
	    color: #333;
	    text-align: center;
	  }
	  .el-collapse-item ul{
	  	background-color: 
	  }
	  .el-collapse-item ul li{
	  	list-style: none;
	  }
	  .el-form-item{
	  	margin-bottom: 10px
	  }
</style>

