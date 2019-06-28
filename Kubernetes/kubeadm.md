# 已知需要镜像 (v1.15.0)
> 官方
```shell
docker pull k8s.gcr.io/kube-apiserver:v1.15.0 \
&& docker pull k8s.gcr.io/kube-controller-manager:v1.15.0 \
&& docker pull k8s.gcr.io/kube-scheduler:v1.15.0 \
&& docker pull k8s.gcr.io/kube-proxy:v1.15.0 \
&& docker pull k8s.gcr.io/pause:3.1 \
&& docker pull k8s.gcr.io/etcd:3.3.10 \
&& docker pull k8s.gcr.io/coredns:1.3.1
```

> 国内
```shell
docker pull registry.cn-hangzhou.aliyuncs.com/ates-k8s/kube-proxy:v1.15.0 \
&& docker tag registry.cn-hangzhou.aliyuncs.com/ates-k8s/kube-proxy:v1.15.0 k8s.gcr.io/kube-proxy:v1.15.0 \

&& docker pull registry.cn-hangzhou.aliyuncs.com/ates-k8s/kube-apiserver:v1.15.0 \
&& docker tag registry.cn-hangzhou.aliyuncs.com/ates-k8s/kube-apiserver:v1.15.0 k8s.gcr.io/kube-apiserver:v1.15.0 \

&& docker pull registry.cn-hangzhou.aliyuncs.com/ates-k8s/kube-scheduler:v1.15.0 \
&& docker tag registry.cn-hangzhou.aliyuncs.com/ates-k8s/kube-scheduler:v1.15.0 k8s.gcr.io/kube-scheduler:v1.15.0 \

&& docker pull registry.cn-hangzhou.aliyuncs.com/ates-k8s/kube-controller-manager:v1.15.0 \
&& docker tag registry.cn-hangzhou.aliyuncs.com/ates-k8s/kube-controller-manager:v1.15.0 k8s.gcr.io/kube-controller-manager:v1.15.0 \

&& docker pull registry.cn-hangzhou.aliyuncs.com/ates-k8s/coredns:1.3.1 \
&& docker tag registry.cn-hangzhou.aliyuncs.com/ates-k8s/coredns:1.3.1 k8s.gcr.io/coredns:1.3.1 \

&& docker pull registry.cn-hangzhou.aliyuncs.com/ates-k8s/etcd:3.3.10 \
&& docker tag registry.cn-hangzhou.aliyuncs.com/ates-k8s/etcd:3.3.10 k8s.gcr.io/etcd:3.3.10 \

&& docker pull registry.cn-hangzhou.aliyuncs.com/ates-k8s/pause:3.1 \
&& docker tag registry.cn-hangzhou.aliyuncs.com/ates-k8s/pause:3.1 k8s.gcr.io/pause:3.1
```