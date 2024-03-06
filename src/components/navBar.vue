<template>
  <el-container>
    <el-aside :width="sidewith+'px'" style="background-color: rgba(96, 48, 122, 0.93);  box-shadow: 2px 0 10px rgba(0, 14, 21, 0.5)">
        <el-menu :default-openeds="['1', '3']" style="min-height: 100%;overflow-x: hidden;"
          background-color="rgba(96, 48, 122, 0.93)"
          text-color="#fff"
          active-text-color="rgba(0, 0, 130, 1)"
          :collapse-transition="false"
          :collapse="isCollapse"
          class="el-minu-vertical-demo">
          <div style="height: 60px; line-height: 60px; text-align: center;">
            <img src="../assets/logo.png" style="width: 20px; position: relative; top: 5px; " >
            <b style="color: #ccc;margin-left: 5px;" v-if="!isCollapse">後臺管理系統</b>
          </div>
          <el-submenu index="1">
            <template slot="title">
              <i class="el-icon-message"></i>
              <span slot="title">导航一</span>
            </template>
            <el-menu-item-group>
              <template slot="title">分组一</template>
                <el-menu-item index="1-1">选项1</el-menu-item>
                <el-menu-item index="1-2">选项2</el-menu-item>
              </el-menu-item-group>

              <el-menu-item-group title="分组2">
                <el-menu-item index="1-3">选项3</el-menu-item>
              </el-menu-item-group>

            <el-submenu index="1-4">
              <template slot="title">选项4</template>
              <el-menu-item index="1-4-1">选项4-1</el-menu-item>
            </el-submenu>

          </el-submenu>

          <el-submenu index="2">

            <template slot="title">
              <i class="el-icon-menu"></i>
              <span slot="title">导航二</span>
            </template>
            <el-menu-item-group>
              <template slot="title">分组一</template>
                <el-menu-item index="2-1">选项1</el-menu-item>
                <el-menu-item index="2-2">选项2</el-menu-item>
              </el-menu-item-group>

              <el-menu-item-group title="分组2">
                <el-menu-item index="2-3">选项3</el-menu-item>
              </el-menu-item-group>

              <el-submenu index="2-4">
                <template slot="title">选项4</template>
              <el-menu-item index="2-4-1">选项4-1</el-menu-item>
            </el-submenu>

          </el-submenu>

          <el-submenu index="3">

            <template slot="title">
              <i class="el-icon-setting"></i>
              <span slot="title">导航三</span>
            </template>
            <el-menu-item-group>
              <template slot="title">分组一</template>
                <el-menu-item index="3-1">选项1</el-menu-item>
                <el-menu-item index="3-2">选项2</el-menu-item>
              </el-menu-item-group>

            <el-menu-item-group title="分组2">
              <el-menu-item index="3-3">选项3</el-menu-item>
            </el-menu-item-group>

            <el-submenu index="3-4">
              <template slot="title">选项4</template>
            <el-menu-item index="3-4-1">选项4-1</el-menu-item>
            </el-submenu>

          </el-submenu>

        </el-menu>
      </el-aside>
  </el-container>
</template>

<script>
export default {
  name: 'navBar',
  props: {
    sidewith: Number,
    isCollapse: Boolean,
  },
  data() {
      return {
        isCollapse: false,
        sidewith: 200,
      }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>./navBar.vue./navbar.vue
