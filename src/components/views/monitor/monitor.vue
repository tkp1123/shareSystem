<template>
  <div class="pd20">
    <el-card shadow="never">
      <el-tabs v-model="activeName" type="card" @tab-click="handleClick">
        <el-tab-pane label="产线状态" name="first">
          <MonitorStatus v-if="activeName == 'first'"></MonitorStatus>
        </el-tab-pane>
        <el-tab-pane label="产线事件监控" name="second">
          <MonitorEvent v-if="activeName == 'second'"></MonitorEvent>
        </el-tab-pane>
      </el-tabs>
    </el-card>
  </div>
</template>
<script>
import MonitorEvent from './template/monitor_event'
import MonitorStatus from './template/monitor_status'
export default {
  //产线监控
  name: 'monitor',
  components: {
    MonitorEvent,
    MonitorStatus,
  },
  data() {
    return {
      activeName: 'first',
    }
  },
  methods: {
    handleClick() {},
  },
}
</script>
<style lang="less" scoped>
.el-table {
  margin-top: 15px;
  font-size: 14px;
}
.el-pagination {
  padding: 10px;
}
</style>