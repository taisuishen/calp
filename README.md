# calp

OKX 合约大额清仓利润计算器（纯静态单页，无后端、无 API key）。支持黄金 XAU、白银 XAG、ALGO 永续。

按 OKX 实时盘口（`/api/v5/market/books`，400 档）从买一往下逐档吃单，算出指定数量的成交均价、总收入与滑点。
再填上持仓成本价，直接给出这笔清仓的净盈亏、收益率、保本均价、手续费与每档累计盈亏。
合约面值和最小报价单位通过 `/api/v5/public/instruments` 获取（XAU-USDT-SWAP 为 0.001 XAU/张，ALGO-USDT-SWAP 为 10 ALGO/张），
填持仓数量即可，自动换算张数，价格小数位按 `tickSz` 自适应。

- 在线地址：部署到 Vercel 后访问根路径
- 本地使用：直接用浏览器打开 `index.html`（桌面端可用；手机上 `file://` 会被浏览器拦截跨域请求，需要走 http(s)）
