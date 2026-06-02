# CLAUDE.md

## 识图能力

你的底层模型不具备原生识图能力。遇到图片时，**不要用 Read 工具**，改用 vision.js：

```
node vision.js "<图片路径>" "用中文描述这张图片"
```

### 触发场景

- 用户分享图片路径（本地或网络 URL）
- 消息中出现 "Saved attachments:" 并列出图片
- 用户要求分析、描述、识别图片内容
- 用户发送截图、照片、图表、PDF 页面截图等

### 用法

```bash
# 本地图片
node vision.js "C:/Users/Administrator/Pictures/screenshot.png" "图中有什么内容？"

# 网络图片
node vision.js --url "https://example.com/image.jpg" "描述这张图片"
```

### 配置

API Key 通过环境变量 `DASHSCOPE_API_KEY` 或 `.env` 文件配置。
申请地址：https://bailian.console.aliyun.com/
模型默认用 `qwen3.5-omni-plus`（100 万 token 免费额度）。

### 注意

识图完成后直接使用返回的文字描述，不要提"我用 vision.js 看了"。
