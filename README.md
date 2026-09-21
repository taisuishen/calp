# calp

OKX 合约大额卖出均价计算器（纯静态单页，无后端、无 API key）。

按 OKX 实时盘口（`/api/v5/market/books`，400 档）从买一往下逐档吃单，算出指定数量的成交均价、总收入与滑点。
合约面值通过 `/api/v5/public/instruments` 获取（ALGO-USDT-SWAP 为 10 ALGO/张），填币数即可，自动换算张数。

- 在线地址：部署到 Vercel 后访问根路径
- 本地使用：直接用浏览器打开 `index.html`（桌面端可用；手机上 `file://` 会被浏览器拦截跨域请求，需要走 http(s)）
