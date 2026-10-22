# portfolio

GitHub Pages 跳转页：访问即跳转到服务器版作品集。

- 在线地址：<https://shuolan009-del.github.io/portfolio/>
- 跳转目标：<https://82.157.150.111/portfolio/wangben/#v03>
- 服务器版本（作品集本体）：<https://82.157.150.111/portfolio/wangben/>

## 行为

`index.html` 是**纯跳转页**，不是作品集内容页——作品集本体托管在 `82.157.150.111`，
GitHub Pages 只承担入口地址。跳转用三重保障：

1. `<meta http-equiv="refresh" content="0; url=...">` —— 0 秒立即跳，禁用 JS 也生效
2. `location.replace()` —— 双保险，且不污染历史记录
3. 可见的手动按钮 —— JS 与 meta 都失效时仍可点击进入

跳转前先 `history.replaceState` 擦掉本页：否则用户按「后退」会被再次弹回服务器版，
形成「后退 → 跳转」的死循环。同理 `404.html` 的返回链接直指服务器版，不链回本页。

`#v03` 锚点原样保留（服务器版页面当前没有对应 id，会停在页首；将来加了锚点即自动生效）。

## 设计

森林绿主色体系（`#2e5f3b` / `#3e7d4f` / `#f4f8f0`）+ Georgia 衬线标题，
提示页居中展示森林树标与「正在前往作品集」。转圈动画尊重 `prefers-reduced-motion`。

## 本地预览

直接双击 `index.html` 即可，无需起服务。注意 `file://` 下部分浏览器会限制
`history.replaceState`，此时由 `meta refresh` 与按钮兜底。

## 已知事项

目标站证书为**自签名**（`CN=82.157.150.111`，签发者 `Jiahe Internal Root CA`，非公共 CA），
浏览器首次访问会弹安全警告「您的连接不是私密连接」，需手动点「高级 → 继续前往」。
