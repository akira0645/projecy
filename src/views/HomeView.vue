<template>
  <el-container style="min-height: 100vh;">
      <navBar :sidewith="sidewith" :isCollapse="isCollapse" />
      <el-container>
        <el-header style=" font-size: 12px; border-bottom: 1px solid #ccc; line-height: 60px;display: flex;">
          <div style="flex:1;font-size: 18px;">
            <span :class="collapseBtnClass" style="cursor: pointer" @click="collapse"></span>
          </div>
          <el-dropdown style="width: 70px; cursor: pointer;">
            <span>王小虎</span>
            <i class="el-icon-arrow-down" style="margin-left: 5px;"></i>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>個人資訊</el-dropdown-item>
              <el-dropdown-item>退出</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
        </el-header>
        
        <el-main>
          <div style="margin: 10px 0;">
            <el-input style="width: 200px; margin-right: 5px;" prefix-icon="el-icon-search" placeholder="請輸入"></el-input>
            <el-button class="ml-5" >搜尋</el-button>
          </div>

          <div style="margin: 10px 0;">
            <el-button class="ml-5" icon="el-icon-circle-plus-outline" >insert</el-button>
            <el-button class="ml-5" icon="el-icon-remove-outline" >delete</el-button>
          </div>
          
          <el-table :data="tableData" height="480"stripe :header-cell-style="{background: 'rgba(211, 150, 224, 0.8)'}">
            <el-table-column prop="date" label="日期" width="140">
            </el-table-column>
            <el-table-column prop="name" label="姓名" width="120">
            </el-table-column>
            <el-table-column prop="address" label="地址">
            </el-table-column>
          </el-table>
          <div style="padding: 10px 0;">
            <el-pagination
            @size-change="handleSizeChange"
            @current-change="handleCurrentChange"
            :current-page="currentPage4"
            :page-sizes="customPageSizes"
            :page-size="10"
            layout="total, sizes, prev, pager, next, jumper"
            :total="400">
            </el-pagination>
          </div>
        </el-main>
      </el-container>
  </el-container>
</template>

<script>
import navBar from '@/components/navBar';
export default {
  name: 'HomeView',
  components:{navBar},
  data() {
    const item = {
        date: '2016-05-02',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1518 弄'
      };
      return {
        tableData: Array(10).fill(item),
        collapseBtnClass:'el-icon-s-fold',
        isCollapse: false,
        sidewith: 200,
        customPageSizes: [5, 10, 20, 50],
      }
  },
  methods:{
    collapse(){
        this.isCollapse=!this.isCollapse
        if(this.isCollapse){
          this.sidewith= 64
          this.collapseBtnClass='el-icon-s-unfold'
        }
        else{
          this.sidewith= 200
          this.collapseBtnClass='el-icon-s-fold'
        }
    }
  }
}
</script>
