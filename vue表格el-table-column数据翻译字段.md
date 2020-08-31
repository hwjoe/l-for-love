# vue表格el-table-column数据翻译字段 #

state传来的是码值，需要转换成汉字，如：1转为成功，2转为失败

```
<el-table-column
  align="center"
  min-width="100px"
  label="状态"
  prop="state"
  :formatter = "stateFormat"
></el-table-column>
```

使用 :formatter = "stateFormat"

在方法区：
```
methods: {
      stateFormat(row, column) {
        console.log(row.state)
        if (row.state === 0) {
          return '未上链'
        } else if (row.state === 1) {
          return '成功'
        } else if (row.state === 2) {
          return '上链失败'
        }
      }
.....
```

链接：https://blog.csdn.net/qq_27721169/article/details/80668176
