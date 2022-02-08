<template>
  <div class="dashboard-container">
    <div class="dashboard-text">name: {{ name }}</div>
    <div>{{ list }}</div>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'
const Mock = require('mockjs')
export default {
  name: 'Dashboard',
  data() {
    return {
      list: []
    }
  },
  computed: {
    ...mapGetters(['name'])
  },
  mounted() {
    console.log(Mock)
    this.list = Mock.mock({
      // 属性 list 的值是一个数组，其中含有 1 到 10 个元素
      'list|1-10': [
        {
          // 属性 id 是一个自增数，起始值为 1，每次增 1
          'id|+1': 1
        }
      ]
    })
  },
  methods: {}
}
</script>

<style lang="scss" scoped>
.dashboard {
  &-container {
    margin: 30px;
  }
  &-text {
    font-size: 30px;
    line-height: 46px;
  }
}
</style>
