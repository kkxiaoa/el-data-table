<template>
  <div class="ts-table--viewer">
    <el-data-table
      v-bind="tableConfig"
      ref="dataTable"
      @selection-change="onSelectionChange"
    ></el-data-table>
  </div>
</template>

<script>
export default {
  name: '',
  data() {
    return {
      tableConfig: {
        url: '/el-table',
        columns: [
          {
            type: 'selection'
          },
          {
            prop: 'temp_name',
            label: '组件名称'
          },
          {
            prop: 'category',
            label: '分类'
          },
          {
            prop: 'version',
            label: '版本'
          },
          {
            prop: 'dev_lang',
            label: '开发语言'
          },
          {
            prop: 'update_time',
            label: '最后更新时间'
          },
          {
            prop: 'status',
            label: '状态',
            formatter: row => (row.status === 'actived' ? '上架' : '下架')
          }
        ],
        searchForm: [
          {
            type: 'input',
            id: 'temp_name',
            label: '组件名称',
            el: {
              placeholder: '请输入'
            }
          },
          {
            type: 'select',
            id: 'category',
            label: '分类',
            el: {
              placeholder: '请输入'
            },
            options: [
              {
                label: '前端组件',
                value: '前端组件'
              },
              {
                label: '服务端组件',
                value: '服务端组件'
              }
            ]
          },
          {
            type: 'select',
            id: 'status',
            label: '状态',
            el: {
              placeholder: '请输入'
            },
            options: [
              {
                label: '上架',
                value: 'actived'
              },
              {
                label: '下架',
                value: 'disabled'
              }
            ]
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
                trigger: 'blur',
                transform: v => v && v.trim()
              }
            ]
          }
        ],
        extraButtons: [
          {
            type: 'warning',
            text: row => (row.status === 'actived' ? '下架' : '上架')
          }
        ],
        hasView: true,
        viewText: '查看',
        editText: '编辑'
      },
      selected: []
    }
  },
  methods: {
    onSelectionChange(val) {
      this.selected = val
    }
  }
}
</script>

<style lang="less"></style>
