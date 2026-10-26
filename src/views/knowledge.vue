<template>
  <div>
    <page-head title="知识文章">
      <template #buttons>
        <el-button type="primary">新增</el-button>
        <el-button type="primary">编辑</el-button>
      </template>
    </page-head>
    <TableSearch :formItem="formItem" @search="handleSearch">

    </TableSearch>
  </div>
</template>
<script setup>
import PageHead from '@/components/PageHead.vue'
import TableSearch from '@/components/TableSearch.vue'

const formItem = [{
  label: '文章标题',
  prop: 'title',
  comp: 'input',
  placeholder: '请输入文章标题',
},
{
  comp: 'select', label: '分类', prop: 'categoryId', options: [
    { label: '心理健康基础', value: 1 }, { label: '情绪管理', value: 2 }], placeholder: '请选择分类'
}
]
const handleSearch = (formData) => {
  console.log(formData,'查询参数')
}
</script>
<style lang="scss" scoped>
.knowledge {
  height: 100%;
}
</style>
