# k3devops

Ultra Lightweight Local MicroService DevOps build on k3d

技术栈选用 `k3d` + `skaffold` 组建开发环境, `DroneCI` 驱动 `CI/CD` 流程

# 开发环境
`MacOS` + `Python2.7.17` + `Ansible2.9.6` + `Emacs26`

# 测试环境
Ubuntu18.04LTS

# 环境安装教程

依赖 `Python2.7` + `Ansible2.9`

## all in one

```sh
ansible-playbook --connection=local --inventory 127.0.0.1, playbook.yml
```

## 安装配置Docker环境

```sh
ansible-playbook --connection=local --inventory 127.0.0.1, playbook.yml --tags=docker
```

## 安装配置k3d+skaffold环境

```sh
ansible-playbook --connection=local --inventory 127.0.0.1, playbook.yml --tags=k3d
```

# 使用教程

## 命令

```sh
ansible-playbook --connection=local --inventory 127.0.0.1, create_example.yml
```

## 开发流程

1. 输入希望创建的项目路径
2. 输入希望创建的编程语言
3. 进入创建的项目目录
4. 执行 `skaffold dev` 进入开发流程
5. 修改代码后自动触发:打包->tag镜像->push本地仓库->渲染k8s部署文件->应用k8s部署流程

## 视频演示

[![asciicast](https://asciinema.org/a/gqt21QYGwq2kL306rBD0pr2Yt.svg)](https://asciinema.org/a/gqt21QYGwq2kL306rBD0pr2Yt)

# TODO

- [ ] Drone本地流程引入
- [ ] GitOps流程引入