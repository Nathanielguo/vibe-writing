# Vibe Writing

> 一款单文件浏览器写作工具，通过 DeepSeek 完成续写、改写与结构优化，并支持将结果导出为常用文本格式。

![HTML5](https://img.shields.io/badge/HTML5-single--file-E34F26?logo=html5&logoColor=white)
![AI](https://img.shields.io/badge/AI-DeepSeek-4D6BFE)
![Storage](https://img.shields.io/badge/storage-localStorage-5A29E4)
![License](https://img.shields.io/badge/license-MIT-2EA44F)

## 🎯 项目定位

Vibe Writing 将常见的文本处理动作集中在一个无需构建的浏览器页面中，适合快速完成初稿推进、表达转换和篇幅调整。它负责提供可编辑的候选文本，最终判断与发布责任仍由使用者承担。

## ✨ 核心功能

- **续写**：沿当前上下文继续生成内容。
- **摘要**：压缩长文本并保留核心信息。
- **正式化 / 口语化**：切换表达语气。
- **精简 / 扩充**：按目标调整篇幅与信息密度。
- **逻辑优化**：改善内容顺序与衔接。
- **本地状态**：通过 `localStorage` 保留相关页面内容。
- **多格式导出**：支持导出为 `TXT`、`Markdown` 和 `HTML`。

## 🔐 隐私与使用边界

> [!IMPORTANT]
> 文本处理请求由浏览器通过 `fetch` 发往 DeepSeek。输入内容会离开当前设备，其处理方式以 DeepSeek 的隐私政策和服务条款为准。

> [!CAUTION]
> AI 输出可能包含事实错误、不恰当表达或与既有作品相似的内容。发布前应进行人工编辑、事实核查和必要的原创性检查。

- 页面使用当前浏览器的 `localStorage`；在共享设备上使用时，请留意本地残留内容。
- 调用模型所需的 API 凭据应由使用者妥善保管，不要提交到仓库或通过截图公开。
- 不要输入无权交由第三方模型服务处理的机密、个人或受限制内容。

## 🚀 运行方式

项目不需要安装依赖或执行构建。

1. 下载或克隆本仓库。
2. 直接打开 `index.html`，或在仓库目录启动静态文件服务：

```bash
python3 -m http.server 8000
```

3. 在浏览器访问 `http://localhost:8000`。
4. 按页面提示配置 DeepSeek API，然后输入文本并选择处理动作。

## 🔄 数据流

```text
原始文本、处理动作与 API 配置
        ↓
浏览器组织请求
        ↓ fetch
DeepSeek
        ↓
生成或改写结果
        ↓
页面继续编辑 / localStorage 保留相关状态 / 导出本地文件
```

仓库为浏览器端单文件实现，不包含独立的项目后端。

## 📄 许可证

本项目采用 [MIT License](./LICENSE)。
