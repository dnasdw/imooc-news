# 评论内容实现（3）
1. 在云函数里使用.unwind() 对数据进行拆分 [参考](https://uniapp.dcloud.io/uniCloud/cf-database?id=unwind)
2. 然后使用 replaceRoot() 重新定义根节点 ，[参考](https://uniapp.dcloud.io/uniCloud/cf-database?id=replaceroot)
3. 通过上面两步，可以实现记录内某个字段的读取返回，并方便进行分页操作


