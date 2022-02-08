<template>
  <div class="container">
    <el-card>
      <el-row>
        <el-col :span="4">
          <div class="item">
            <div class="img_box">
              <el-image
                style="width: 100%; height: auto;"
                src="https://pic.8666.yyimg.cc/8666/uploads/uploads/allimg/191206/b95446ab90c9782e.jpg"
                fit
              />
              <div class="time">2011</div>
              <div class="mark">5.6分</div>
              <div class="total">共1集,完结</div>
            </div>
            <div class="name">电影名字</div>
            <div class="info">大卫·科波菲尔</div>
          </div>
        </el-col>
        <el-col :span="4">
          <div class="container" />
        </el-col>
        <el-col :span="4">
          <div class="container" />
        </el-col>
        <el-col :span="4">
          <div class="container" />
        </el-col>
        <el-col :span="4">
          <div class="container" />
        </el-col>
        <el-col :span="4">
          <div class="container" />
        </el-col>
      </el-row>
    </el-card>
  </div>
</template>

<script>
import Mock from 'mockjs'
export default {
  components: {},
  data() {
    return {
      year: '2021',
      month: 12,
      day: 31,
      hour: 24,
      minute: 60,
      second: 60
    }
  },
  computed: {},
  mounted() {
    const list = Mock.mock({
      'items|5': [
        {
          id: '@id',
          title: '@sentence(10, 20)',
          'status|1': ['published', 'draft', 'deleted'],
          author: 'name',
          display_time: '@datetime',
          pageviews: '@integer(300, 5000)',

          dbName: 'name',
          dbType: '@natural(1, 7)',
          connectionString: '@string("lower", 10, 30)',
          isEnable: '@boolean(1, 2, true)',
          isDirectConnection: '@boolean(1, 2, true)',
          lastSyncStatus: '@natural(1, 4)',
          lastSyncTime: '@datetime'
        }
      ]
    })
    console.log(list)
  },
  methods: {}
}
</script>

<style scoped lang='scss'>
.container {
  padding: 0 120px;
  .el-card {
    padding: 10px;
    .item {
      display: flex;
      flex-direction: column;
      .img_box {
        position: relative;
        .time,
        .mark,
        .total {
          position: absolute;
        }
        .time {
          left: 5px;
          top: 5px;
          padding: 0 5px;
          font-size: 12px;
          border-radius: 2px;
          color: #fff;
          background-color: coral;
        }
        .mark {
          right: 5px;
          top: 5px;
          background-color: rgba(0, 0, 0, 0.6);
          color: #fff;
          padding: 2px 5px;
          font-size: 12px;
          border-radius: 2px;
        }
        .total {
          display: block;
          width: 100%;
          bottom: 0;
          left: 0;
          padding: 5px 10px;
          font-size: 12px;
          overflow: hidden;
          text-overflow: ellipsis;
          -o-text-overflow: ellipsis;
          white-space: nowrap;
          text-align: right;
          color: #fff;
        }
      }
      .name {
        color: #333;
        font-size: 15px;
        font-weight: 700;
      }
      .info {
        font-size: 12px;
        color: #999;
      }
    }
  }
}
</style>
