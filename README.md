# Huajun Lu · 个人主页

基于 [Academic Pages](https://github.com/academicpages/academicpages.github.io) 的个人学术主页，包含简介、研究与项目、CV，以及独立阅读笔记博客的入口。

站点地址：**https://wall-breakerl.github.io/personal-homepage/**。通过 GitHub Actions 构建并发布到 GitHub Pages，推送 `main` 后自动更新。英文内容根据已有简历整理。

## 本地运行

使用 Ruby **3.3.12** 与 Bundler；依赖版本由 `Gemfile.lock` 固定。

```sh
git clone https://github.com/Wall-breakerL/personal-homepage.git
cd personal-homepage
bundle config set --local path vendor/bundle
bundle install
bundle exec jekyll serve --host 127.0.0.1 --port 4000 --strict_front_matter
```

浏览器访问 `http://localhost:4000/personal-homepage/`。修改 `_config.yml` 后需重启预览。

## 编辑内容

| 内容 | 文件 |
|---|---|
| 个人信息与站点配置 | `_config.yml` |
| 首页简介 | `_pages/about.md` |
| 研究与项目 | `_pages/projects.md` |
| CV | `_pages/cv.md` |
| 导航 | `_data/navigation.yml` |
| 头像 | `images/avatar.png` |

## 构建

```sh
bundle exec jekyll build --strict_front_matter
```

生成的 `_site/`、依赖目录 `vendor/` 和本地 `.bundle/` 配置均不进入 Git。

## 发布

`.github/workflows/pages.yml` 使用固定的 Ruby 与 Bundler 版本构建。GitHub Pages 的发布来源设置为 GitHub Actions。`_config.yml` 已配置项目子路径，内部链接通过 `relative_url` 或模板的 `base_path` 生成。

独立博客源码：[reading-notes](https://github.com/Wall-breakerL/reading-notes)。

## 模板来源

Academic Pages 基于 Minimal Mistakes；本项目保留模板的 [MIT 许可证](LICENSE)。来源版本为 `3d28cd27d0551b3d9dd8132f207538355fbbc7cc`。除填入个人内容外，调整了桌面页脚，避免覆盖长页面正文。

本仓库通过 GitHub Fork 保留与上游的关联。MIT 不要求使用 fork，但要求保留许可证与版权声明；发布产物中的 `licenses/` 提供模板及相关组件的许可说明。
