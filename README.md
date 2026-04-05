# 科技艺术家 on X｜Tech Artists on X

一个聚焦于 X（Twitter）平台上**科技艺术家**的交互式 3D 可视化项目——探索数字艺术、生成艺术、AI 艺术、新媒体艺术领域的创作者、策展人、机构及媒体，以及他们之间的关联网络。

> 基于 [x.mitbunny.ai](https://x.mitbunny.ai) 开源项目进行二次开发，数据与主题全面替换为科技艺术领域。

---

## 🌐 在线访问

**[https://mintingdawn.github.io/tech-artists-x/](https://mintingdawn.github.io/tech-artists-x/)**

---

## 💡 为什么要做这个

科技艺术是一个高度分散的领域——生成艺术、AI Art、创意编程、数据艺术、沉浸式装置……这些创作者分布在世界各地，彼此之间有着密切但不易察觉的关联。

我想把这张隐形的网络**可视化出来**：谁是这个领域的核心节点？哪些机构在推动边界？哪些艺术家之间彼此关注、相互影响？

这个项目是一张**科技艺术生态地图**，也是一个发现新创作者的导航工具。

---

## ✨ 功能特性

- 🌐 **3D 交互式图谱** — 300 位科技艺术家及其关联关系的立体网络
- 🔍 **实时搜索** — 按名字、简介快速找到创作者
- 🗂 **分类筛选** — artist / collective / curator / institution / media 五大类别
- 🌍 **国籍筛选（中文）** — 按国家 / 地区过滤，了解全球分布
- 👤 **创作者卡片** — 展示粉丝数、简介、所在地、国籍、个人网站
- 🔗 **直达 X 主页** — 一键跳转到对应的 X 账号

---

## 🗂 数据说明

**300 位创作者**，筛选标准如下：

| 维度 | 标准 |
|------|------|
| **粉丝门槛** | ≥ 1,500 |
| **关键词（必含）** | AI art, generative art, new media, digital art, creative coding, machine learning art, interactive installation, bio art, VR/AR, computational art, algorithmic art, glitch art, projection mapping, immersive art 等 |
| **关键词（屏蔽）** | crypto, NFT, investment, trading, marketing, agency |
| **种子账号** | 15–20 个多元权威账号（艺术节、策展人、代表性艺术家、垂直媒体） |
| **计分公式** | `分值 = log10(粉丝数) × (权威种子关联数 × 类型权重)` |
| **地域平衡** | 覆盖 40+ 国家和地区 |

分类权重：策展人关联 ×1.5，机构 ×1.2，媒体 ×1.0，艺术家 ×1.0

---

## 🛠 技术栈

| 层级 | 技术 |
|------|------|
| 框架 | React 18 + TypeScript |
| 构建工具 | esbuild |
| 3D 可视化 | Three.js + react-force-graph-3d |
| 样式 | Tailwind CSS |
| 图标 | Lucide React |
| 托管 | GitHub Pages |

---

## 🚀 本地运行

**环境要求：** Node.js

```bash
# 安装依赖
npm install

# 开发模式
npm run dev

# 构建生产版本
node_modules/.bin/esbuild index.tsx --bundle --outfile=dist/bundle.js \
  --loader:.tsx=tsx --loader:.ts=ts --loader:.css=css \
  --jsx=automatic --platform=browser --target=es2020 --minify
```

---

## 📁 项目结构

```
tech-artists-x/
├── App.tsx              # 主应用组件（含侧边栏、筛选、卡片）
├── components/
│   └── Graph3D.tsx      # 3D 图谱渲染组件
├── constants.ts         # 300 位艺术家数据集
├── types.ts             # TypeScript 类型定义
├── index.tsx            # 入口文件
├── index.html           # HTML 模板
├── dist/                # 构建输出（GitHub Pages 托管）
│   ├── index.html
│   └── bundle.js
└── gen_artists.py       # 数据生成脚本
```

---

## 🙏 致谢

- 原始项目：[AI Influencers on X](https://x.mitbunny.ai) by [@Jenny_the_Bunny](https://github.com/mit-bunny)
- 3D 图谱库：[react-force-graph-3d](https://github.com/vasturiano/react-force-graph)
- 数据来源：X (Twitter) 公开账号信息

---

## 📄 License

MIT
