# CentOS-Base
```shell
mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.bak
cat << EOF > /etc/yum.repos.d/CentOS-Base.repo
[base]
name=CentOS-\$releasever - Base
failovermethod=priority
baseurl=https://mirrors.aliyuncs.com/centos/\$releasever/os/\$basearch/
        https://mirrors.aliyun.com/centos/\$releasever/os/\$basearch/
        https://mirrors.tuna.tsinghua.edu.cn/centos/\$releasever/os/\$basearch/
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7
 
#released updates 
[updates]
name=CentOS-\$releasever - Updates
failovermethod=priority
baseurl=https://mirrors.aliyuncs.com/centos/\$releasever/updates/\$basearch/
        https://mirrors.aliyun.com/centos/\$releasever/updates/\$basearch/
        https://mirrors.tuna.tsinghua.edu.cn/centos/\$releasever/updates/\$basearch/
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7
 
#additional packages that may be useful
[extras]
name=CentOS-\$releasever - Extras
failovermethod=priority
baseurl=https://mirrors.aliyuncs.com/centos/\$releasever/extras/\$basearch/
        https://mirrors.aliyun.com/centos/\$releasever/extras/\$basearch/
        https://mirrors.tuna.tsinghua.edu.cn/centos/\$releasever/extras/\$basearch/
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7
 
#additional packages that extend functionality of existing packages
[centosplus]
name=CentOS-\$releasever - Plus
failovermethod=priority
baseurl=https://mirrors.aliyuncs.com/centos/\$releasever/centosplus/\$basearch/
        https://mirrors.aliyun.com/centos/\$releasever/centosplus/\$basearch/
        https://mirrors.tuna.tsinghua.edu.cn/centos/\$releasever/centosplus/\$basearch/
gpgcheck=1
enabled=0
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7
EOF
yum makecache
```
# elrepo
```shell
rpm --import https://www.elrepo.org/RPM-GPG-KEY-elrepo.org
cat << EOF > /etc/yum.repos.d/elrepo.repo
[elrepo]
name=ELRepo.org Community Enterprise Linux Repository - el7
baseurl=https://mirrors.tuna.tsinghua.edu.cn/elrepo/elrepo/el7/\$basearch/
#mirrorlist=http://mirrors.elrepo.org/mirrors-elrepo.el7
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-elrepo.org
protect=0

[elrepo-testing]
name=ELRepo.org Community Enterprise Linux Testing Repository - el7
baseurl=https://mirrors.tuna.tsinghua.edu.cn/elrepo/testing/el7/\$basearch/
#mirrorlist=http://mirrors.elrepo.org/mirrors-elrepo-testing.el7
enabled=0
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-elrepo.org
protect=0

[elrepo-kernel]
name=ELRepo.org Community Enterprise Linux Kernel Repository - el7
baseurl=https://mirrors.tuna.tsinghua.edu.cn/elrepo/kernel/el7/\$basearch/
#mirrorlist=http://mirrors.elrepo.org/mirrors-elrepo-kernel.el7
enabled=0
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-elrepo.org
protect=0

[elrepo-extras]
name=ELRepo.org Community Enterprise Linux Extras Repository - el7
baseurl=https://mirrors.tuna.tsinghua.edu.cn/elrepo/extras/el7/\$basearch/
#mirrorlist=http://mirrors.elrepo.org/mirrors-elrepo-extras.el7
enabled=0
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-elrepo.org
protect=0
EOF
```

# epel
```shell
yum install epel-release
mv /etc/yum.repos.d/epel.repo /etc/yum.repos.d/epel.repo.bak
cat << EOF > /etc/yum.repos.d/epel.repo
[epel]
name=Extra Packages for Enterprise Linux 7 - \$basearch
baseurl=https://mirrors.aliyuncs.com/epel/7/\$basearch
        https://mirrors.aliyun.com/epel/7/\$basearch
        https://mirrors.tuna.tsinghua.edu.cn/epel/7/\$basearch
failovermethod=priority
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-7

[epel-debuginfo]
name=Extra Packages for Enterprise Linux 7 - $basearch - Debug
baseurl=https://mirrors.aliyuncs.com/epel/7/\$basearch/debug
        https://mirrors.aliyun.com/epel/7/\$basearch/debug
        https://mirrors.tuna.tsinghua.edu.cn/epel/7/\$basearch/debug
failovermethod=priority
enabled=0
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-7
gpgcheck=1

[epel-source]
name=Extra Packages for Enterprise Linux 7 - \$basearch - Source
baseurl=https://mirrors.aliyuncs.com/epel/7/SRPMS
        https://mirrors.aliyun.com/epel/7/SRPMS
        https://mirrors.tuna.tsinghua.edu.cn/epel/7/SRPMS
failovermethod=priority
enabled=0
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-7
gpgcheck=1
EOF
```