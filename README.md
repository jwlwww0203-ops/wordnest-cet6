# 拾词 · Wordnest CET6

拍照识别纸面英文，听读音、看释义和场景例句，每天轻量复习。当前应用版本：4.2。

## 源码与发布

完整静态源码、词库、OCR 模型及第三方许可说明保存在 `wordnest-source.zip` 中，解压后的目录为 `site/`。

GitHub Pages 由 `.github/workflows/pages.yml` 发布：读取仓库、解压静态文件、上传 Pages 构建产物并发布。发布流程不会修改仓库内容。

## 本地预览

```sh
python -m zipfile -e wordnest-source.zip .
python -m http.server 8080 --directory site
```

## 更新网站

解压后修改 `site/` 内文件，重新打包为同名 `wordnest-source.zip`（保留 `site/` 顶层目录），提交到 `main` 后自动发布。更新词库时同时调整 `sw.js` 缓存版本与 `word-lookup.js` 词库版本，避免旧缓存继续使用。

## 使用边界

- 收藏和复习进度目前保存在当前浏览器的 localStorage 中，不是云端账号数据。
- 新旧域名的浏览器数据独立，迁移网址不会自动迁移收藏。
- 常用词库和 OCR 随网站提供；词库外查词仍可能请求外部词典。
- GitHub Pages 发布成功不代表所有中国大陆网络都能稳定直连，需在实际网络验证。
- 本次迁移保留原有第三方许可文件，没有为整个项目新增开源许可。
