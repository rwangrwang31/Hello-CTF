# Vercel 部署指南 / Vercel Deployment Guide

这是 Hello CTF 项目的 Vercel 部署配置文件。

## 部署步骤 / Deployment Steps

### 1. 导入到 Vercel / Import to Vercel

1. 访问 [Vercel](https://vercel.com/)
2. 点击 "Import Project"
3. 选择此 GitHub 仓库

### 2. 配置设置 / Configuration Settings

Vercel 会自动检测 `vercel.json` 配置文件。主要配置包括：

- **Framework Preset**: None (使用自定义配置)
- **Build Command**: `uv pip install --system -r requirements.txt && mkdocs build`
- **Output Directory**: `site`
- **Install Command**: `uv pip install --system -r requirements.txt`
- **Python Version**: 3.9.17 (在 `runtime.txt` 中指定)

**注意**: Vercel 现在使用 `uv` 管理 Python 环境，因此需要使用 `uv pip install --system` 命令来安装依赖包。

### 3. 环境变量 / Environment Variables

无需额外的环境变量。

### 4. 自定义域名 / Custom Domain

如果您想使用自定义域名（如 hello-ctf.com）：

1. 在 Vercel 项目设置中，进入 "Domains"
2. 添加您的域名
3. 按照 Vercel 提供的 DNS 配置说明更新您的域名 DNS 记录

`docs/CNAME` 文件已包含域名配置。

### 5. 部署区域 / Deployment Region

Vercel 自动使用全球边缘网络部署，确保全球范围内的快速访问。

## 配置文件说明 / Configuration Files

### vercel.json
- 定义构建命令和输出目录
- 配置路由和缓存策略
- 设置部署区域

### runtime.txt
- 指定 Python 运行时版本（3.9.17）

### .vercelignore
- 排除不需要上传到 Vercel 的文件
- 优化部署大小和速度

## 本地测试 / Local Testing

```bash
# 安装依赖
pip install -r requirements.txt

# 构建站点
mkdocs build

# 本地预览
mkdocs serve
```

访问 http://localhost:8000 查看效果。

## 注意事项 / Notes

1. **图片链接**：所有图片链接已优化为相对路径或外部 CDN 链接
2. **构建时间**：通常需要 8-10 秒
3. **自动部署**：推送到主分支后会自动触发 Vercel 部署
4. **缓存策略**：
   - 静态资源（CSS/JS/图片）：缓存 1 年
   - HTML 文件：必须重新验证

## 故障排除 / Troubleshooting

如果部署失败，请检查：

1. Python 版本是否正确（3.9.17）
2. requirements.txt 中的依赖是否完整
3. mkdocs.yml 配置是否正确
4. 构建日志中的具体错误信息

## 更多信息 / More Information

- [Vercel 文档](https://vercel.com/docs)
- [MkDocs Material 文档](https://squidfunk.github.io/mkdocs-material/)
- [项目主页](https://hello-ctf.com/)
