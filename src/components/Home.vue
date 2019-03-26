<template>
  <el-container>
    <el-header>
      <div class="logo">
        <img src="../assets/img/logo.png" alt="">
        <span>dth飞防作业管理系统</span>
      </div>
    </el-header>
    <el-container>
      <el-aside width="isCollpase?64px:201px">
        <el-menu class="el-menu-vertical-demo"
                 title="展开"
                 @open="handleOpen"
                 @close="handleClose"
                 :collapse="isCollapse"
                 :router="true">
          <el-button
            type="primary"
            icon="el-icon-caret-right"
            title="展开菜单"
            @click="openMenu"
            size="mini"
            style="width: 65px;"
            v-show="isCollapse"
          >
          </el-button>
          <el-button
            type="primary"
            icon="el-icon-caret-left"
            title="收起菜单"
            @click="closeMenu"
            size="mini" style="width: 201px;margin-left: 0;"
            v-show="!isCollapse"
          >
          </el-button>
          <el-submenu index="1">
            <template slot="title">
              <i class="el-icon-location"></i>
              <span slot="title">导航一</span>
            </template>
            <el-menu-item-group>
              <span slot="title">分组一</span>
              <el-menu-item index="1-1">选项1</el-menu-item>
              <el-menu-item index="1-2">选项2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="分组2">
              <el-menu-item index="1-3">选项3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="1-4">
              <span slot="title">选项4</span>
              <el-menu-item index="1-4-1">选项1</el-menu-item>
            </el-submenu>
          </el-submenu>
          <el-menu-item index="2">
            <i class="el-icon-menu"></i>
            <span slot="title">导航二</span>
          </el-menu-item>
          <el-menu-item index="3" disabled>
            <i class="el-icon-document"></i>
            <span slot="title">导航三</span>
          </el-menu-item>
          <el-menu-item index="4">
            <i class="el-icon-setting"></i>
            <span slot="title">导航四</span>
          </el-menu-item>
        </el-menu>
      </el-aside>
      <el-main>Main
        <router-view/>
      </el-main>
    </el-container>
  </el-container>
</template>

<script>
export default {
  data () {
    return {
      isCollapse: false,
      isButtonShow: true
    }
  },
  methods: {
    handleOpen (key, keyPath) {
      console.log(key, keyPath)
    },
    handleClose (key, keyPath) {
      console.log(key, keyPath)
    },
    openMenu () {
      this.isCollapse = false
    },
    closeMenu () {
      this.isCollapse = true
    }
  }
}
</script>

<style scoped lang="less">
  .el-container {
    height: 100%;
    .el-header {
      background-image: linear-gradient(to right , #00CC99, #00FF99);
      .logo {
        display: inline-block;
        height: 100%;
        position: relative;
        user-select: none;
        img {
          height: 50px;
          margin-top: 5px;
        }
        span {
          display: inline-block;
          width: 300px;
          position: absolute;
          top: 0;
          left: 80px;
          height: 60px;
          line-height: 60px;
          font-size: 30px;
          font-weight: 700;
        }
      }
    }
    .el-aside {
      /*background-image: linear-gradient(to bottom, #CC9933, #CCCC66);*/
    }
    .el-main {
      background-color: #eaedf1;
    }
  }
  .el-menu-vertical-demo:not(.el-menu--collapse) {
    width: 200px;
    min-height: 400px;
  }
</style>
