> 安装
```shell
yum install nfs-utils
```

> server
```markdown
修改/etc/exports
格式:
共享文件路径 可访问共享的CIRD(选项)
选项: (逗号分隔)
r - 只读
rw - 读写
sync - 同步
async - 异步

e.g. /shared/xxx 10.0.0.0/8(rw,async)
```
