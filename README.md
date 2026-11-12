# portfolio

GitHub Pages 跳转页：访问即跳转到服务器版作品集。

- 在线地址：<https://shuolan009-del.github.io/portfolio/>
- 跳转目标：<https://1.92.109.214/portfolio/wangben/>
- 服务器版本（作品集本体）：<https://1.92.109.214/portfolio/wangben/>

## 行为

`index.html` 是**纯跳转页**，不是作品集内容页——作品集本体托管在 `1.92.109.214`，
GitHub Pages 只承担入口地址。跳转用三重保障：

1. `<meta http-equiv="refresh" content="0; url=...">` —— 0 秒立即跳，禁用 JS 也生效
2. `location.replace()` —— 双保险，且不污染历史记录
3. 可见的手动按钮 —— JS 与 meta 都失效时仍可点击进入

跳转前先 `history.replaceState` 擦掉本页：否则用户按「后退」会被再次弹回服务器版，
形成「后退 → 跳转」的死循环。同理 `404.html` 的返回链接直指服务器版，不链回本页。

目标地址按服务器实际路径给定，不带锚点；如将来需要定位到具体版本区块，在 URL 末尾加 `#xxx` 即可。

## 设计

森林绿主色体系（`#2e5f3b` / `#3e7d4f` / `#f4f8f0`）+ Georgia 衬线标题，
提示页居中展示森林树标与「正在前往作品集」。转圈动画尊重 `prefers-reduced-motion`。

## 本地预览

直接双击 `index.html` 即可，无需起服务。注意 `file://` 下部分浏览器会限制
`history.replaceState`，此时由 `meta refresh` 与按钮兜底。

## 已知事项

目标站 `1.92.109.214` 使用 **Let's Encrypt 签发的 IP 证书**（SAN 含 `IP:1.92.109.214`，
2026-11-10 签发，约 90 天有效、自动续期），浏览器访问**无**安全警告。
（此前托管在 `82.157.150.111` 时为自签名证书，会弹「您的连接不是私密连接」，需手动放行。）
