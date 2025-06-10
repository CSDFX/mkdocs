# 软件包管理器
包管理器（Package Manager）是用于安装、升级、配置和管理软件包的工具

### Yum、Dnf、Apt
 Yum 和 Dnf 是红帽系 Linux 所广泛使用的软件包管理器，它为用户提供了便捷的软件包安装、更新、管理等功能。Dnf 是 Yum 的增强版，不仅继承了 Yum 的核心功能，还在性能、用户体验等方面进行了诸多优化。在使用上，Dnf 与 Yum 非常相似，两者在命令层面基本相同，只是名字有所区别。

APT(Advanced Package Tool) 是 Debian 系 Linux 发行版中使用的软件包管理工具。

### 使用方法
#### 安装软件包
=== "Yum"

    ```
    yum install <package-name>
    ```

=== "Dnf"

    ```
    dnf install <package-name>
    ```

=== "Apt"

    ```
    apt install <package-name>
    ```

#### 移除软件包
=== "Yum"

    ```
    yum remove <package-name>
    ```

=== "Dnf"

    ```
    dnf remove <package-name>
    ```

=== "Apt"

    ```
    apt remove <package-name>
    ```
更多命令详见：[Linux yum 命令](https://www.runoob.com/linux/linux-yum.html)