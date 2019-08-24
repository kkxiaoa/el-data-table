<template>
 <div class="ts-table--viewer">
   <el-data-table v-bind="tableConfig"></el-data-table>
 </div>
</template>

<script>
export default {
 name: '',
 data() {
  return {
    tableConfig: {
      url: '/example/users',
      columns: [
        {
          type: 'select'
        },
        {
          prop: 'templateName',
          label: '组件名称'
        },
        {
          prop: '',
          label: '分类'
        },
        {
          prop: '',
          label: '版本'
        },
        {
          prop: '',
          label: '开发语言'
        },
        {
          prop: '',
          label: '最后更新时间'
        },
        {
          prop: '',
          label: '状态'
        }
      ],
      searchForm: [
        {
          type: 'input',
          id: 'name',
          label: '组件名称',
          el: {
            placeholder: '请输入'
          }
        },
        {
          type: 'select',
          id: 'type',
          label: '分类',
          el: {
            placeholder: '请输入'
          },
          options: [{
            label: 'shanghai',
            value: 'shanghai'
          }, {
            label: 'beijing',
            value: 'beijing'
          }]
        },
        {
          type: 'select',
          id: 'status',
          label: '状态',
          el: {
            placeholder: '请输入'
          },
          options: [{
            label: 'shanghai',
            value: 'shanghai'
          }, {
            label: 'beijing',
            value: 'beijing'
          }]
        }
      ],
      form: [
        {
          type: 'input',
          id: 'name',
          label: '组件名称',
          el: {
            placeholder: '请输入'
          },
          rules: [
            {
              required: true,
              message: '组件名称',
              trigger: 'blur'
            }
          ]
        }
      ]
    }
  }
 },
 components: {

 }
}
</script>

<style lang="less">
 
</style>
