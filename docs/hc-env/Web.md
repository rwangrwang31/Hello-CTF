# Web 环境配置

## 前言

本文档旨在帮助您快速搭建 Web 安全学习和 CTF 比赛所需的环境。Web 方向的学习需要掌握基本的网络知识、编程基础以及常用的渗透测试工具。

!!! tip "推荐学习路径"
    建议在学习 Web 安全之前，先掌握以下基础知识：
    
    - HTML/CSS/JavaScript 基础
    - HTTP 协议基础
    - 至少一门后端语言（PHP/Python/Java）
    - Linux 基本操作
    - SQL 数据库基础

## 系统环境

### 推荐系统

- **主力系统**：Windows 10/11 或 macOS（日常使用）
- **虚拟机系统**：Kali Linux 或 Ubuntu（用于渗透测试工具）

### 虚拟机软件

| 软件名称 | 说明 | 下载地址 |
|---------|------|---------|
| VMware Workstation Pro | Windows/Linux 推荐 | [官网](https://www.vmware.com/products/workstation-pro.html) |
| VMware Fusion | macOS 推荐 | [官网](https://www.vmware.com/products/fusion.html) |
| VirtualBox | 开源免费方案 | [官网](https://www.virtualbox.org/) |

## 开发环境

### 文本编辑器 / IDE

| 工具名称 | 用途 | 下载地址 |
|---------|------|---------|
| Visual Studio Code | 轻量级代码编辑器，支持多种语言 | [官网](https://code.visualstudio.com/) |
| PHPStorm | PHP 专业开发环境 | [官网](https://www.jetbrains.com/phpstorm/) |
| PyCharm | Python 专业开发环境 | [官网](https://www.jetbrains.com/pycharm/) |
| IDEA | Java 专业开发环境 | [官网](https://www.jetbrains.com/idea/) |

### 本地 Web 环境

对于初学者，建议使用集成环境快速搭建本地测试环境：

| 工具名称 | 平台 | 说明 | 下载地址 |
|---------|------|------|---------|
| PHPStudy | Windows/Linux/macOS | 支持 Apache/Nginx + MySQL + PHP | [官网](https://www.xp.cn/) |
| XAMPP | Windows/Linux/macOS | Apache + MySQL + PHP + Perl | [官网](https://www.apachefriends.org/) |
| WAMP | Windows | Windows + Apache + MySQL + PHP | [官网](https://www.wampserver.com/) |
| MAMP | macOS | macOS + Apache + MySQL + PHP | [官网](https://www.mamp.info/) |

### Docker 环境

对于进阶学习和比赛，强烈推荐使用 Docker 来部署题目环境：

- **Docker Desktop**：[官网下载](https://www.docker.com/products/docker-desktop)
- **配置教程**：参见 [Docker环境配置](Docker_On_Linux.md)

!!! warning "注意"
    Docker 是现代 CTF 比赛的标准部署方式，建议尽早掌握 Docker 的基本使用。

## 浏览器配置

### 推荐浏览器

- **Chrome / Edge**：推荐用于日常测试和开发
- **Firefox**：推荐用于渗透测试（配合 Burp Suite）

### 浏览器插件

以下插件可以极大提升 Web 安全学习效率：

| 插件名称 | 用途 | 安装方式 |
|---------|------|---------|
| HackBar | 快速编辑和发送 HTTP 请求 | Chrome 应用商店 |
| Wappalyzer | 识别网站使用的技术栈 | Chrome 应用商店 |
| EditThisCookie | Cookie 编辑器 | Chrome 应用商店 |
| Proxy SwitchyOmega | 代理切换管理 | Chrome 应用商店 |

## 渗透测试工具

### 抓包工具

| 工具名称 | 说明 | 下载地址 |
|---------|------|---------|
| Burp Suite | 最强大的 Web 安全测试工具 | [官网](https://portswigger.net/burp) |
| Yakit | 国产安全测试工具 | [官网](https://www.yaklang.com/) |

**Burp Suite 配置步骤：**

1. 下载并安装 Burp Suite Community Edition
2. 启动 Burp Suite，默认代理端口为 `127.0.0.1:8080`
3. 配置浏览器代理指向 `127.0.0.1:8080`
4. 安装 Burp 证书（用于 HTTPS 抓包）

### 常用命令行工具

以下工具通常在 Kali Linux 中预装，如使用其他系统需要手动安装：

| 工具名称 | 用途 | 安装方式 |
|---------|------|---------|
| sqlmap | SQL 注入自动化工具 | `pip install sqlmap` |
| dirsearch | 目录扫描工具 | `pip install dirsearch` |
| nikto | Web 服务器扫描工具 | Kali 预装 |
| nmap | 端口扫描工具 | Kali 预装 |

### WebShell 管理工具

| 工具名称 | 说明 | 下载地址 |
|---------|------|---------|
| 蚁剑 (AntSword) | 开源 WebShell 管理工具 | [GitHub](https://github.com/AntSwordProject/antSword) |
| 冰蝎 (Behinder) | 动态二进制加密 WebShell 客户端 | [GitHub](https://github.com/rebeyond/Behinder) |
| 哥斯拉 (Godzilla) | WebShell 管理工具 | [GitHub](https://github.com/BeichenDream/Godzilla) |

## 数据库工具

| 工具名称 | 说明 | 下载地址 |
|---------|------|---------|
| Navicat | 专业的数据库管理工具 | [官网](https://www.navicat.com.cn/) |
| DBeaver | 开源免费的数据库管理工具 | [官网](https://dbeaver.io/) |
| phpMyAdmin | Web 版 MySQL 管理工具 | 通常集成在环境包中 |

## Python 环境配置

很多 Web 题目的脚本编写需要 Python，建议安装以下模块：

```bash
# 基础库
pip install requests
pip install beautifulsoup4
pip install lxml

# 安全工具库
pip install pwntools
pip install pycryptodome

# Web 框架（用于本地搭建测试）
pip install flask
pip install django
```

## 学习资源

### 在线靶场

- [NSSCTF](https://www.nssctf.cn/) - 国内优秀的 CTF 平台
- [BugKu](https://ctf.bugku.com/) - Web 安全入门靶场
- [攻防世界](https://adworld.xctf.org.cn/) - XCTF 官方平台
- [Hack The Box](https://www.hackthebox.com/) - 国际知名渗透测试平台

### 推荐教程

- 本书 [Web | 网络攻防](../hc-web/index.md) 章节
- [CTFtools-wiki](https://github.com/ProbiusOfficial/CTFtools-wiki) - 工具使用教程
- [CTF-Wiki](https://ctf-wiki.org/) - CTF 知识库

## 环境验证

完成环境配置后，可以通过以下方式验证：

### 1. 本地 Web 环境测试

创建一个简单的 PHP 文件 `test.php`：

```php
<?php
phpinfo();
?>
```

访问 `http://localhost/test.php`，如果能看到 PHP 配置信息页面，说明环境配置成功。

### 2. Burp Suite 测试

1. 启动 Burp Suite
2. 配置浏览器代理
3. 访问任意网站
4. 在 Burp Suite 的 Proxy > HTTP history 中查看是否捕获到请求

### 3. Python 工具测试

```bash
# 测试 requests 库
python -c "import requests; print(requests.get('http://www.baidu.com').status_code)"

# 如果输出 200，说明配置成功
```

## 常见问题

### Burp Suite 无法抓取 HTTPS

**解决方案**：需要安装 Burp CA 证书

1. 浏览器访问 `http://burp`（需开启代理）
2. 点击右上角的 "CA Certificate" 下载证书
3. 将证书导入浏览器的受信任根证书颁发机构

### PHPStudy 端口被占用

**解决方案**：

1. 查看 80 端口占用：`netstat -ano | findstr :80`
2. 结束占用进程或修改 PHPStudy 配置使用其他端口

### Docker 无法启动

**解决方案**：参见 [Docker环境配置](Docker_On_Linux.md) 中的故障排除部分

## 下一步

环境配置完成后，建议：

1. 学习 [Web入门题单](../hc-web/web_start.md) 中的基础题目
2. 熟悉 Burp Suite 的基本使用
3. 在靶场上进行实战练习
4. 阅读本书 Web 章节的各个知识点

!!! success "完成配置"
    恭喜你完成了 Web 方向的环境配置！现在可以开始你的 Web 安全学习之旅了。
