<template>
  <div class="home">
      <el-container style="height: 500px; border: 1px solid #eee">

          <el-aside width="200px" style="background-color: rgb(238, 241, 246)">
              <!--                动态设置 menu  注意 index 属性必须是 字符串类型的 -->
              <el-menu router :default-openeds="['0', '1']">
                  <el-submenu v-for="(item, index) in $router.options.routes" :index="index + ''" v-if="item.show">
                      <template slot="title"><i class="el-icon-menu"></i>{{item.name}}</template>
                      <el-menu-item v-for="(item2, index2) in item.children" :index="item2.path"
                        :class="item2.path==$route.path?'is-active':''">{{item2.name}}</el-menu-item>
                  </el-submenu>
              </el-menu>

          </el-aside>

          <el-container>
              <el-header syarn run servetyle="text-align: right; font-size: 12px">
<!--                  <el-dropdown>-->
<!--                      <i class="el-icon-setting" style="margin-right: 15px"></i>-->
<!--                      <el-dropdown-menu slot="dropdown">-->
<!--                          <el-dropdown-item>查看</el-dropdown-item>-->
<!--                          <el-dropdown-item>新增</el-dropdown-item>-->
<!--                          <el-dropdown-item>删除</el-dropdown-item>-->
<!--                      </el-dropdown-menu>-->
<!--                  </el-dropdown>-->
<!--                  <span>王小虎</span>-->
              </el-header>


              <el-main>
                  <router-view/>
              </el-main>
          </el-container>

      </el-container>
  </div>
</template>

<script>
// @ is an alias to /src


export default {
  name: 'Home',
  components: {

  }
}
</script>
