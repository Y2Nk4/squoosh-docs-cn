# squoosh-docs-cn
GoogleChromeLabs/squoosh Chinese Docs

Original Repository / 原始仓库: [GoogleChromeLabs/squoosh](https://github.com/GoogleChromeLabs/squoosh/blob/dev/README.md)

更新于 2020.12.12

# [Squoosh]!

[Squoosh] 是一个可以让你深入了解各种图像压缩器的高级选项的网页应用

# CLI

[Squoosh 已拥有 CLI 支持](https://github.com/GoogleChromeLabs/squoosh/tree/dev/cli) 
你可以用这个cli工具一次性压缩多张图片 (对应汉化文档: [Squoosh CLI](cli/README.md))

# 隐私说明

本项目使用 Google Analytics 记录以下内容

- [基本的访问数据](https://support.google.com/analytics/answer/6004245?ref_topic=2919631).
- 被下载的图片在压缩前与压缩后的大小，数值会被四舍五入到kb
- 安装 Squoosh 后，会记录 Squoosh 的安装方式

图片压缩是在本地进行的，其余的数据不会被发送到服务器。

# 本地构建

克隆原仓库, 然后执行:

```sh
npm install
npm run build
```

或使用以下命令以开发模式启动:

```sh
npm start
```

[squoosh]: https://squoosh.app
