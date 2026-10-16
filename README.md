# portfolio

个人作品集静态页，部署在 GitHub Pages。

- 源文件：`index.html`（单文件，零依赖，零构建）
- 在线地址：<https://shuolan009-del.github.io/portfolio/>
- 服务器版本：<https://82.157.150.111/portfolio/>

## 设计

- 森林绿主色体系（`#2e5f3b` / `#3e7d4f` / `#f4f8f0`），Georgia 衬线标题 + 无衬线正文
- 入场动画为**渐进增强**：内容默认可见，仅在支持动画的环境下由 JS 加 `.anim` 类播放，
  并有 2.5s 兜底强制显示——保证爬虫截图 / 禁用 JS / `prefers-reduced-motion` 下内容完整可读
- 响应式：860px 断点切换单列；尊重 `prefers-reduced-motion`

## 四个项目

| # | 项目 | 链接 |
|---|---|---|
| 01 | 嘉禾智能商管平台 | <https://82.157.150.111/> |
| 02 | AI 电商客服 | <https://82.157.150.111/cs/> |
| 03 | AI 电商运营助手 | <https://github.com/shuolan009-del/ecommerce-operation-assistant> |
| 04 | AI 知识库 | <https://github.com/shuolan009-del/knowledge-base> |

## 本地预览

直接双击 `index.html` 即可，无需起服务。
