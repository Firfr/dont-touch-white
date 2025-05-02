# 别踩白块 don`t touch white

春节无聊写的

[试玩](https://qishaoxuan.github.io/dont-touch-white)


## 部署说明

当前汉化仅适用于 版本：

首先感谢原作者的开源。[原项目地址](https://github.com/QiShaoXuan/dont-touch-white)

本人提供这个项目在 NAS、服务器等的有偿远程部署服务，有需要可联系。  
微信号 `E-0_0-`  
闲鱼搜索用户 `明月人间`  
或者邮箱 `firfe163@163.com`  
如果这个项目有帮到你。欢迎start。

有其他的项目的汉化需求，欢迎提issue。或其他方式联系通知。

### 镜像

从阿里云或华为云镜像仓库拉取镜像，注意填写镜像标签，镜像仓库中没有`latest`标签

容器内部端口 3000 可通过设置环境变量`MINISERVE_PORT`的值来指定监听端口

```bash
docker pull swr.cn-north-4.myhuaweicloud.com/firfe/dont-touch-white:2025.05.02
```

### docker run 命令部署

```bash
docker run -d \
--name dont-touch-white \
--network bridge \
--restart always \
--log-opt max-size=1m \
--log-opt max-file=3 \
-p 3000:3000 \
swr.cn-north-4.myhuaweicloud.com/firfe/dont-touch-white:2025.05.02
```
### compose 文件部署 👍推荐

```yaml
#version: '3.9'
services:
  dont-touch-white:
    container_name: dont-touch-white
    image: swr.cn-north-4.myhuaweicloud.com/firfe/dont-touch-white:2025.05.02
    network_mode: bridge
    restart: always
    logging:
      options:
        max-size: 1m
        max-file: '3'
    ports:
      - 3000:3000
```

## 修改说明
 
增加修改部分具体见 [修改说明](./修改说明.md)。

`./README.md` 增加 `## 部署说明`、`## 修改说明`、`## 效果截图` 部分。

增加目录 `./图片`
新增文件 `./.dockerignore`、`./Dockerfile`、`./修改说明.md`

## 效果截图

<img src="图片/效果图.png" width="500" />

