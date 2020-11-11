<template>
  <div class="menu-wrap" ref="menuWrap">
    <el-row :gutter="20">
      <el-col :span="5" v-for="item in projects" :key="item">
        <el-card shadow="hover" class="card">
          <img class="p-icon" :src="`${$baseUrl}image/menu/cli.png`" alt="" />
          <p>{{ item }}</p>
        </el-card>
      </el-col>
      <el-col :span="5">
        <el-card shadow="hover" class="card">
          <img class="p-icon" src="@/assets/img/httpswww.qq.comfromd.png" alt="" />
          <p>联系我</p>
        </el-card>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import CanvasNest from 'canvas-nest.js'
const config = {
  color: '0,0,0',
  pointColor: '255,0,0',
  opacity: '1',
  count: 200
}
export default {
  data () {
    return {
      projects: ['ff-cli', 'ff-music', 'ff-大屏']
    }
  },
  mounted () {
    this.cn = new CanvasNest(this.$refs.menuWrap, config)
  },
  beforeDestroy () {
    this.cn.destroy()
  }
}
</script>

<style lang="scss" scoped>
.menu-wrap {
  height: 100%;
  padding: 10px;
  .card {
    text-align: center;
    background: #fbfcfd;
    .p-icon {
      height: 80px;
    }
    p {
      font-size: 18px;
      color: #1f2d3d;
    }
  }
}
</style>
