# 博客系统使用指南

欢迎使用你的博客系统！这个指南将帮助你理解博客系统的结构，以及如何添加新的博客文章。

## 📁 目录结构

```
homepage/
├── blog.html                    # 博客列表页面
├── BLOG_GUIDE.md               # 本文件
├── blog/                        # 博客文章目录
│   ├── 001-欢迎来到我的博客.html
│   ├── 002-链式思维研究.html
│   └── 003-暗物质探测.html
└── assets/blog-assets/         # 博客相关资源
    ├── thumbnails/             # 博客文章缩略图（可选）
    └── styles/                 # 博客自定义样式（可选）
```

## 🚀 快速开始

### 访问博客
- **博客列表页面**：访问 `blog.html`
- **单篇文章**：点击博客卡片或在博客列表中选择文章
- **从主页访问**：点击导航栏中的"📝 Blog"链接

### 添加新文章

#### 方法1：复制现有模板

1. 复制 `blog/001-欢迎来到我的博客.html` 文件
2. 重命名为 `blog/XXX-你的文章标题.html`
3. 编辑文章内容
4. 在 `blog.html` 中的 `blogPosts` 数组中添加对应的条目

#### 方法2：使用模板代码

```html
<!DOCTYPE HTML>
<html lang="en">

<head>
  <!-- Google Analytics -->
  <script async src="https://www.googletagmanager.com/gtag/js?id=G-R4HCHY9LYJ"></script>
  <script>
    window.dataLayer = window.dataLayer || [];
    function gtag() { dataLayer.push(arguments); }
    gtag('js', new Date());
    gtag('config', 'G-R4HCHY9LYJ');
  </script>

  <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="author" content="Zhizheng Zhao">
  <meta name="description" content="你的文章描述">

  <title>你的文章标题 - Zhizheng Zhao</title>

  <!-- Favicon -->
  <link rel="shortcut icon" href="../assets/favicon/android-chrome-512x512.png" type="image/x-icon">

  <!-- Responsive stylesheets -->
  <link rel="stylesheet" href="../desktop.css" media="screen and (min-width: 601px)">
  <link rel="stylesheet" href="../mobile.css" media="screen and (max-width: 600px)">
  <link rel="stylesheet" href="../desktop.css" media="print">

  <!-- Article styles (保持不变) -->
  <style>
    /* 样式代码 - 复制自现有文章 */
  </style>
</head>

<body>
  <div class="article-container">
    <!-- 修改以下内容 -->
    <div class="article-header">
      <h1 class="article-title">你的文章标题</h1>
      <div class="article-meta">
        <span>📅 2025年XX月XX日</span>
        <span>✍️ 赵志政</span>
        <span>🏷️ 分类</span>
      </div>
      <div class="tags">
        <span class="tag">标签1</span>
        <span class="tag">标签2</span>
      </div>
    </div>

    <div class="article-content">
      <!-- 你的文章内容 -->
      <h2>标题1</h2>
      <p>段落内容...</p>
    </div>

    <div class="article-footer">
      <a href="../blog.html" class="back-link">← 返回博客列表</a>
    </div>
  </div>
</body>

</html>
```

## 📝 在 blog.html 中添加文章

编辑 `blog.html` 中的 `blogPosts` 数组，添加新的对象：

```javascript
const blogPosts = [
  {
    id: 4,                              // 唯一ID，递增
    title: "你的文章标题",
    date: "2025-11-15",                 // YYYY-MM-DD 格式
    category: "分类",                   // 如：技术、物理、个人感想等
    excerpt: "简短的文章摘要...",
    tags: ["标签1", "标签2"],           // 标签数组
    url: "blog/004-你的文章标题.html"   // 文章文件路径
  },
  // ... 其他文章
];
```

## 🎨 文章格式指南

### 标题层级
```html
<h2>一级标题（文章主要章节）</h2>
<h3>二级标题（小节）</h3>
```

### 文本格式
```html
<p>普通段落</p>

<ul>
  <li>无序列表项</li>
  <li>无序列表项</li>
</ul>

<ol>
  <li>有序列表项</li>
  <li>有序列表项</li>
</ol>

<blockquote>引用文本</blockquote>

<code>行内代码</code>

<pre><code>代码块</code></pre>
```

## 📊 分类建议

根据你的研究方向，建议的分类包括：

- **技术** - 深度学习、AI、编程等技术文章
- **物理** - 暗物质、粒子物理等物理学相关
- **研究** - 研究进展、论文分享等
- **个人感想** - 学习心得、生活感悟等
- **学习笔记** - 学科笔记、教程整理等

## 🏷️ 标签管理

标签用于分类和搜索，建议：
- 每篇文章3-5个标签
- 使用相关、具体的标签
- 保持标签命名一致

## 💡 提示

1. **日期格式**：始终使用 `YYYY-MM-DD` 格式，以便正确排序
2. **文章URL**：确保文件路径与实际创建的文件一致
3. **中文支持**：系统完全支持中文，可放心使用
4. **响应式设计**：所有样式已针对移动设备优化
5. **SEO**：记得填写 `<meta>` 标签中的描述（description）

## 🔍 文章发现优化

### 添加缩略图（可选）

如果想为文章添加缩略图：
1. 将图片保存到 `assets/blog-assets/thumbnails/`
2. 在 `blog.html` 的 `blogPosts` 中添加 `thumbnail` 字段
3. 修改博客列表卡片的 HTML 显示缩略图

### 分类导航（可选）

如果文章很多，可以在 `blog.html` 中添加分类过滤功能。

## 常见问题

### Q: 如何删除文章？
A:
1. 删除对应的 `.html` 文件
2. 从 `blog.html` 的 `blogPosts` 数组中删除对应条目

### Q: 如何修改文章顺序？
A:
修改 `blog.html` 中 `blogPosts` 数组中元素的顺序。新文章通常放在最前面。

### Q: 如何修改博客样式？
A:
编辑 `blog.html` 中 `<style>` 部分的 CSS，或编辑单篇文章 HTML 中的样式。

### Q: 可以添加评论功能吗？
A:
目前是静态网站。如要添加评论，可以整合第三方服务如 Disqus、Utterances 等。

## 📚 相关文件

- `blog.html` - 博客列表页面，管理所有文章的元数据
- `blog/*.html` - 个别博客文章文件
- `desktop.css` / `mobile.css` - 基础样式（继承自主页）
- `BLOG_GUIDE.md` - 本指南文件

## 🎯 下一步

1. ✅ 博客系统已建立
2. ✅ 添加了3篇样本文章
3. 📝 开始写你自己的文章
4. 🚀 定期更新新内容
5. 💬 与读者互动（可选：添加社交分享）

---

祝你的博客写作愉快！如有任何问题，欢迎联系。 📝✨
