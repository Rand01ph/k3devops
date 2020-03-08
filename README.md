# k3devops

Ultra Lightweight Local MicroService DevOps build on k3d

Poor Man's DevOps

技术栈选用 `k3d` + `skaffold` 组建开发环境, `DroneCI` 驱动 `CI/CD` 流程

使用Docker镜像作为代码交付形态,适合各种语言的本地开发流程(目前有Golang简易脚手架示例)

# 开发环境
`MacOS` + `Python2.7.17` + `Ansible2.9.6` + `Emacs26`

# 测试环境
Ubuntu18.04LTS

# 环境安装教程

## 安装依赖

 `Python2.7` + `Ansible2.9`

## 安装方式

### all in one (Docker+k3s+skaffold安装配置)

```sh
ansible-playbook --connection=local --inventory 127.0.0.1, playbook.yml
```

### 安装配置Docker

```sh
ansible-playbook --connection=local --inventory 127.0.0.1, playbook.yml --tags=docker
```

### 安装配置k3d+skaffold

```sh
ansible-playbook --connection=local --inventory 127.0.0.1, playbook.yml --tags=k3d
```

# 使用教程

## 创建开发脚手架

```sh
ansible-playbook --connection=local --inventory 127.0.0.1, create_example.yml
```

## 脚手架开发流程

1. 输入希望创建的项目路径
2. 输入希望创建的编程语言
3. 进入创建的项目目录
4. 执行 `skaffold dev` 进入开发流程
5. 修改代码后自动触发:打包->tag镜像->push本地仓库->渲染k8s部署文件->应用k8s部署流程

## 视频演示

[![asciicast](https://asciinema.org/a/gqt21QYGwq2kL306rBD0pr2Yt.svg)](https://asciinema.org/a/gqt21QYGwq2kL306rBD0pr2Yt)

# TODO

- [ ] MacOS自动化部署支持
- [ ] Web Framework脚手架示例
- [ ] 更多编程语言脚手架示例(Python,Node.js...)
- [ ] Drone本地流程引入