# ArgoSB Python 版本

## 简介

这是 ArgoSB 脚本的 Python 版本，无需 root 权限，**完全适用于普通用户**。所有文件安装在用户主目录下的`.agsb`隐藏文件夹中，不会影响系统目录。脚本使用 Python 3，**仅使用 Python 标准库**，无需安装额外依赖。

## 使用方法

### 免费 vps 免 root 一键安装 hysteria2

```bash
systemctl stop firewalld && cd ~ && curl -fsSL https://raw.githubusercontent.com/zhiact/agsb/main/hysteria2-v1.py | python3 -


```

## 或者（免费 vps 免 root 一键安装 vmess）

```bash
systemctl stop firewalld && cd ~ && cd ~ && curl -fsSL https://raw.githubusercontent.com/zhiact/agsb/main/agsb-v2.py | python3 - install --uuid b1ebd5fc-9170-45d4-9887-a39c9fc65298 --port 49999 --agk CF-token --domain 自己的域名

```

### 固定域名一键安装命令

```bash
cd ~ && curl -fsSL https://raw.githubusercontent.com/zhiact/agsb/main/agsb-v2.py | python3 - install --uuid b1ebd5fc-9170-45d4-9887-a39c9fc65298 --port 49999 --agk CF-token --domain 自己的域名

```

## 或者

```bash
cd ~ && wget https://raw.githubusercontent.com/zhiact/agsb/main/agsb.py && python3 agsb.py install --uuid 25bd7521-eed2-45a1-a50a-97e432552aca --port 49999 --agk CF-token --domain 自己的域名
```

### 一键安装命令

```bash
cd ~ && wget https://raw.githubusercontent.com/zhiact/agsb/main/agsb.py && python3 agsb.py
```

```bash
cd ~ && wget https://raw.githubusercontent.com/zhiact/agsb/main/frpsb.py -O frpsb.py&& python3 frpsb.py
```

## 或者

```bash
cd ~ && curl -fsSL https://raw.githubusercontent.com/zhiact/agsb/main/agsb.py | python3 -
```

### 安装

```bash
python3 agsb.py install
```

首次运行会自动安装并配置服务。安装完成后会创建`~/bin/agsb`命令链接，可直接使用`agsb`命令操作。

### 启动服务

```bash
agsb
# 或
python3 agsb.py
```

### 查看服务状态

```bash
agsb status
# 或
python3 agsb.py status
```

### 查看单行节点列表

```bash
agsb cat
# 或
python3 agsb.py cat
```

### 升级脚本

```bash
agsb update
# 或
python3 agsb.py update
```

### 卸载服务

```bash
agsb uninstall
# 或
python3 agsb.py del
```

## 环境变量设置

可以通过环境变量自定义配置：

- `vmpt`: 指定 vmess 端口
- `uuid`: 指定 UUID
- `agn`: 指定 Argo 固定域名
- `agk`: 指定 Argo 授权密钥

例如：

```bash
export vmpt=10000
export uuid=your-uuid
python3 agsb.py
```

## 安装目录

所有文件安装在用户主目录下的`.agsb`隐藏文件夹内：

- `~/.agsb/sing-box`: sing-box 可执行文件
- `~/.agsb/cloudflared`: cloudflared 可执行文件
- `~/.agsb/sb.json`: sing-box 配置文件
- `~/.agsb/list.txt`: 节点信息列表
- `~/.agsb/allnodes.txt`: 单行节点列表文件

## 优点

1. **无需 root 权限**，普通用户即可使用
2. 安装在用户主目录下的隐藏文件夹，不影响系统目录
3. 使用 Python 3 编写，语法更现代
4. **仅使用标准库**，无需安装任何额外依赖
5. 保留了原 shell 脚本的所有核心功能
6. 自动创建用户目录下的命令链接，使用更方便
7. 更友好的错误处理和调试信息
8. 提供直接输出节点功能，方便复制使用

## 兼容性提示

- 需要 Python 3 环境，无需安装额外的依赖
- 所有文件都安装在用户目录下，不影响系统目录
- 安装完成后会在`~/bin`目录创建命令链接，如需使用，请确保该目录在 PATH 环境变量中
