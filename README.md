# Docker Nginx reverse 反向代理

此项目用于配合 [Docker LAMP](https://github.com/getnas/lamp) 使用。

当主机上多个 Docker 容器均需要映射 `80` 端口时（例如，多个网站），则使用本项目作为反响代理服务器。

### 使用方法

    # 克隆项目到本地
    git clone https://github.com/getnas/nginx-reverse.git
    # 进入项目目录
    cd nginx-reverse
    # 修改配置文件
    nano ./conf/default.conf
    # 启动容器
    docker-compose up -d

### 注意事项

此容器将在主机启动一个默认开放 `80` 端口的容器，因此启动此容器前请停止或修改其他占用 `80` 端口的程序或容器以防发生端口冲突。

所有需要 `80` 端口转发的容器分别设置成不同的端口号，为了便于记忆和识别可以选择 `8000`、`8010`、`8020` 等等。

修改此项目中 `./conf/default.conf` 参照样本填写你实际需要使用的域名、IP及端口。
