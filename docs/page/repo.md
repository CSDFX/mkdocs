# 镜像源

Linux 镜像源（也称为**软件源**或 **软件仓库** ）是存储和分发 Linux 系统及其软件包的服务器或服务器集群。用户通过包管理器（如 `apt`、`yum`、`dnf`、`zypper` 等）从镜像源下载安装系统更新和软件。

### 一、镜像源的作用

1. **软件获取** ：提供系统软件包和第三方应用。
2. **系统更新** ：系统升级和安全补丁通过镜像源分发。
3. **依赖管理** ：软件依赖项可自动从镜像源下载。
4. **加速下载** ：镜像站点通常提供高速网络连接，提升下载速度。

### 二、镜像源的组成

一个镜像源一般包含：

* **主服务器** （官方源）和多个 **镜像站** （第三方同步源）。
* 不同的 **目录结构** ，对应不同的发行版本、架构、软件分类等。
* 通常支持 HTTP、HTTPS、FTP 协议访问。

### 三、为什么更换镜像源

1. **提升速度** ：默认源可能在国外，速度慢或不稳定。
2. **本地化支持** ：使用就近高校或企业维护的镜像站可大幅提升更新效率。
3. **安全性与稳定性** ：官方认证镜像站安全可靠，减少损坏包或中断风险。

### Example：
更换镜像源为阿里源
=== "CentOS Linux 7"
    ```
    curl -o /etc/yum.repos.d/CentOS-Base.repo https://mirrors.aliyun.com/repo/Centos-7.repo
    ```

=== "Debian 12"
    ```
    sed -i 's|deb.debian.org|mirrors.aliyun.com|g' /etc/apt/sources.list.d/debian.sources
    ```
更换本地源
=== "CentOS Linux 7"
    ```
    vi /etc/yum.repos.d/Centos-Media.repo
	    baseurl=file:///mnt/
	    enabled=1
    rm -rf /etc/yum.repos.d/Centos-Base.repo
    mount /dev/cdrom /mnt
    ```

=== "Rocky Linux 9.x"
    ```
    vim /etc/yum.repos.d/rocky.repo
        [baseos]
        name=Rocky Linux $releasever - BaseOS
        #mirrorlist=https://mirrors.rockylinux.org/mirrorlist?arch=$basearch&repo=BaseOS-$releasever$rltype
        baseurl=file:///mnt/BaseOS
        gpgcheck=1
        enabled=1
        countme=1
        metadata_expire=6h
        gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-Rocky-9

        [appstream]
        name=Rocky Linux $releasever - AppStream
        #mirrorlist=https://mirrors.rockylinux.org/mirrorlist?arch=$basearch&repo=AppStream-$releasever$rltype
        baseurl=file:///mnt/AppStream
        gpgcheck=1
        enabled=1
        countme=1
        metadata_expire=6h
        gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-Rocky-9

    mount /dev/cdrom /mnt
    ```
使用Nginx搭建一个网络源
```
yum -y install nginx
mount /dev/cdmnt /usr/share/nginx/
systemctl start nginx
```