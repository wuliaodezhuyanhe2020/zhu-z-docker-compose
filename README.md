# 使用文档 —— `zhu-z-docker-compose`

使用`docker-compose`快速部署服务

### 一、环境准备

1. #### 安装`Docker`

   ```sh
   ## 把yum更新到最新
   $ yum update
   ## 检查Docker是否安装
   $ docker -v
   > Docker version XX.X.X, build xxxxx
   ## 卸载Docker，如果没有安装，则不需要这一步
   $ yum remove -y docker*
   ## 安装Docker所需要的工具包
   $ yum install -y yum-utils
   ## 建立Docker映射仓库
   $ yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
   ## 安装最新版Docker
   $ yum install docker-ce docker-ce-cli containerd.io
   ## 启动Docker
   $ systemctl start docker
   ## 测试Docker是否正常运行
   $ docker run hello-world
   ## 检查正在运行的容器
   $ docker ps
   ```

2. #### 安装`docker-compose`

   ```sh
   ## 上传docker-compose文件到/usr/local/bin/目录下
   ## docker-compose文件在zhu-z-docker-compose/Linux/目录下
   ## 添加可执行权限
   $ chmod +x /usr/local/bin/docker-compose
   ## 创建docker-compose的软链接
   $ ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
   ## 测试安装结果
   $ docker-compose --version
   > Docker Compose version v2.23.3
   ```

3. #### 配置镜像加速器（可选）

   ###### 访问[容器镜像服务](https://cr.console.aliyun.com/cn-beijing/instances/mirrors)获取**加速器地址**

   ```sh
   sudo mkdir -p /etc/docker
   sudo tee /etc/docker/daemon.json <<-'EOF'
   {
     "registry-mirrors": ["<加速器地址>"]
   }
   EOF
   sudo systemctl daemon-reload
   sudo systemctl restart docker
   ```

4. #### `Git`

   ```sh
   ## 安装git命令
   $ yum install -y git
   ## 从仓库拉取zhu-z-docker-compose
   $ git clone https://gitee.com/wuliaodezhuyanhe-2020/zhu-z-docker-compose.git
   ```

### 二、运行服务

> 环境部署见每个服务下的`xxx.md`
>
> 例：MySQL  >  zhu-z-docker-compose/MySQL/MySQL8/MySQL8.md

### 三、服务分类

​	该模块可以快速导航到所需服务，目前还在制作中，敬请期待！

