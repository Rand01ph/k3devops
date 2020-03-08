# k3devops
Local DevOps build on k3d

# 环境
Ubuntu18.04 测试通过

# 使用

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
