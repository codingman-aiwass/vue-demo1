<script>
export default {
  name: "Header"
}
</script>

<template>
  <div style="height: 50px; line-height: 50px; border-bottom: 1px solid #ccc;display: flex">
    <div style="width: 200px;padding-left: 10px;font-weight: bold">Backend Management</div>
    <div style="flex: 1"></div>
    <div style="width: 100px;padding-top: 10px">
      <div class="flex flex-wrap items-center">
        <el-dropdown>
          <el-button >
            Chan<el-icon class="el-icon--right"><arrow-down /></el-icon>
          </el-button>
          <template #dropdown>
            <el-dropdown-menu>
              <el-dropdown-item>Personal Info</el-dropdown-item>
              <el-dropdown-item>Exit</el-dropdown-item>
            </el-dropdown-menu>
          </template>
        </el-dropdown>
      </div>
    </div>
  </div>
</template>

<style scoped>
</style>