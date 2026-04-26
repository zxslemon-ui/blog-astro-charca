# 个人博客搭建
> 搭建半自动化平台，在本地完成 MD 文档编写并上传后，自动部署至 Web 端

## 技术选型

+ 前端 Node.js 框架：Astro
+ 代码托管：GitHub
+ 网站自动部署：Vercel

## 主要技术栈
+ Astro (v6.1.5)：核心框架，用于静态站点生成和组件化开发
+ @astrojs/mdx：支持在 Markdown 中嵌入组件
+ @astrojs/rss 和 @astrojs/sitemap：自动生成 RSS 订阅和站点地图
+ Sharp：图像优化
+ TypeScript：类型安全配置

## 开始部署

```bash
# 使用 npm 创建
npm init astro -- --template Charca/astro-blog-template
```

### 项目结构
```plain
. (项目根目录)
/
├── public/
│   ├── robots.txt
│   └── favicon.ico
├── src/
│   ├── components/
│   │   └── Tour.astro
│   └── pages/
│       └── index.astro
└── package.json
```

Astro 会查找 `src/pages/` 目录中的 `.astro` 或 `.md` 文件。每个页面都根据其文件名暴露为一个路由。

`src/components/` 目录没有什么特别的，但那是我们喜欢放置任何 Astro/React/Vue/Svelte/Preact 组件的地方。

任何静态资源，比如图片，都可以放在 `public/` 目录中。

### 相关命令
所有命令都在项目的根目录下，通过终端运行，更多命令可查看[官方技术文档](https://docs.astro.build/)：

| Command | Action |
| --- | --- |
| `npm install` | Installs dependencies |
| `npm run dev` | Starts local dev server at `localhost:4321` |
| `npm run build` | Build your production site to `./dist/` |
| `npm run preview` | Preview your build locally, before deploying |
| `npm run astro ...` | Run CLI commands like `astro add`<br/>, `astro check` |
| `npm run astro -- --help` | Get help using the Astro CLI |


### 上传至 GitHub
#### 创建 GitHub 项目仓库
此步骤略过

#### 本地 push 至 GitHub 云端
```bash
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/ username/repository.git
git push -u origin main
```

### 使用 Vercel 自动部署网站
#### 通过网站 UI 部署
1. 将你的代码推送到你的在线 Git 存储库（GitHub、GitLab、BitBucket 等）。
2. [导入你的项目](https://vercel.com/new) 至 Vercel。
3. Vercel 将自动检测 Astro 项目并自动为其配置正确的设置。
4. 你的应用程序已部署完成了！（例如：[astro.vercel.app](https://astro.vercel.app/)）

> 前往 [网站部署](https://docs.astro.build/zh-cn/guides/deploy/vercel/) 页了解详情
>

## 项目优化
请前往[项目搭建记录](./src/data/blog-posts/building-records.md)查看