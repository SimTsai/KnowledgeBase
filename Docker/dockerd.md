> /etc/docker/daemon.json
```json
{
  "exec-opts": ["native.cgroupdriver=systemd"],
  "log-driver": "json-file",
  "log-opts": {
    "max-size": "100m"
  },
  "storage-driver": "overlay2",
  "storage-opts": [
    "overlay2.override_kernel_check=true"
  ],
  "debug": false,
  "exec-root": "<DOCKER_EXEC_PATH>",  # docker exec 存储位置
  "data-root": "<DOCKER_DATA_PATH>",  # docker data 存储位置
  "experimental": true,
  "registry-mirrors": ["https://xxxx"] # 国内镜像
}
```
[registry-mirrors获取方式参考](https://help.aliyun.com/document_detail/60750.html?spm=a2c4g.11174283.6.549.47004541Qq30AF)