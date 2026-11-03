# 安装 WSL（Ubuntu 20.04）

## 1. 一键安装（推荐）

前提：Windows 10 版本 2004+ 或 Windows 11。

 打开「控制面板 → 程序 → 启用或关闭 Windows 功能」，勾选「适用于 Linux 的 Windows 子系统」和「虚拟机平台」两项，点击「确定」，完成后按提示重启电脑。 
    ![图片](img/wmx001.png)

打开cmd

按'win+R'输入'cmd'

执行安装命令

```powershell
wsl --install -d Ubuntu-20.04
```
其中 `Ubuntu-20.04` 里的 `20.04` 是发行版版本号，可按需替换；该命令需要下载并安装完整系统，耗时较长。

设置 Linux 用户名和密码。

注意：密码输入时不显示任何字符，盲打回车即可

安装后更新软件源

```bash
sudo apt update && sudo apt upgrade
```

## 2. 删除 WSL

### 1. 备份需要保留的发行版

`wsl --unregister` 会永久删除指定发行版中的文件、软件和设置。只是暂时不用时，可以先用 `wsl --terminate 发行版名` 停止它；需要清除环境时，先备份再注销。

以下命令在 Windows PowerShell 中执行。先用 `wsl --list --verbose` 查看准确名称，下面以 `Ubuntu-20.04` 为例：

```powershell

## 安装后核对发行版状态

在 Windows PowerShell 或命令提示符中查看已安装的发行版及其 WSL 版本：

```powershell
wsl --list --verbose
wsl --status
wsl --version
```

在列表中确认目标发行版名称，并查看 `VERSION` 列。若项目需要 WSL 2，而发行版显示为 1，可先备份重要文件，再按需转换：

```powershell
wsl --set-version Ubuntu-20.04 2
```

`wsl --update` 更新 WSL 组件；进入 Ubuntu 后运行 `sudo apt update && sudo apt upgrade` 更新 Linux 软件包。这两项更新针对不同部分。更多命令见[微软 WSL 基本命令](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands)。
