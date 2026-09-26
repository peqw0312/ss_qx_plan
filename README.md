# ss_qx_plan

个人自用的 Quantumult X 分流配置 —— 基于「墨鱼自用QX配置 2.0」做了一轮针对性定制。

> ⚠️ 本仓库是**个人自用版本**，不是墨鱼官方发布，也**未获原作者授权**。
> 想要原版请去：<https://ddgksf2013.top/Profile/QuantumultX.conf>

---

## 仓库内容

| 路径 | 说明 |
| --- | --- |
| `QuantumultX.conf` | 主配置，可直接导入 Quantumult X |
| `docs/` | 5 份中文文档：使用说明 / 规则总清单 / 导入后验证清单 / 体检与优化方案 / 去广告清单与卡顿排查 |
| `icons/` | 自绘的节点图标（方版，用于替换尺寸不统一的旧图标） |

## 来源与致谢

本配置基于 [@ddgksf2013](https://github.com/ddgksf2013)（墨鱼手记）的
**「墨鱼自用QX配置 2.0」** 修改而成：

- 原配置：<https://ddgksf2013.top/Profile/QuantumultX.conf>
- TG 频道：[@ddgksf2021](https://t.me/ddgksf2021)

配置文件头部**完整保留了原作者的署名块与 changelog** —— 这是刻意保留的，请连同本段一起保留。

配置中另外引用了以下作者的成果：

- **图标**：[Orz-3](https://github.com/Orz-3/mini)、[Koolson](https://github.com/Koolson/Qure)
- **分流规则**：[blackmatrix7](https://github.com/blackmatrix7/ios_rule_script)、[ConnersHua](https://github.com/ConnersHua/RuleGo)、[Cats-Team](https://github.com/Cats-Team/AdRules)、[VirgilClyne](https://github.com/VirgilClyne)
- **脚本 / 重写**：[chavyleung](https://github.com/chavyleung/scripts)、[KOP-XIAO](https://github.com/KOP-XIAO/QuantumultX)

**原配置及上述各项资源，版权归各自作者所有。本仓库仅为个人自用定制版，禁止任何商业用途。**

## 相对原版改了什么

| # | 主题 | 改动 |
| --- | --- | --- |
| 1 | 精简 | 远程规则集 19 → 14 套；重写 18 → 10 条；删掉 4 个已无人引用的空策略组 |
| 2 | 兜底改直连 | `final, direct` —— 国内流量天然直连，不再依赖 `geoip, cn` 判断 |
| 3 | 本地直连白名单 | 加密货币交易所（Binance / OKX / Bybit / Bitget 及自带钱包）、国产 AI（豆包 / DeepSeek / Kimi / 智谱 / 通义 等）、常见国内服务 |
| 4 | Soul 改属地 | 单独策略组 + 走代理，让 Soul 显示海外 IP |
| 5 | 地区测速组 | 在原有港台日新美基础上，新增 **韩国 / 英国 / 大马 / 德国 / 火鸡（土耳其）** |
| 6 | 图标统一 | 大马节点图标重绘为方版，与 Orz-3 那套同规格（见 `icons/`） |
| 7 | 修一个卡顿 | 远程规则里 `opt.doubao.com` 被 reject 导致豆包启动变慢，用本地白名单盖掉 |

完整逐条记录写在 `QuantumultX.conf` 文件头的「共 17 处改动」里。

## 怎么用

### 方式一 · 订阅导入（推荐）

1. 打开 Quantumult X → 「设置」→ 「配置文件」→ 「导入」
2. 粘贴下面的地址：

```
https://raw.githubusercontent.com/<你的GitHub用户名>/ss_qx_plan/main/QuantumultX.conf
```

> 国内网络直连 `raw.githubusercontent.com` 可能失败，可加加速前缀：
> `https://ghproxy.net/https://raw.githubusercontent.com/<你的GitHub用户名>/ss_qx_plan/main/QuantumultX.conf`

### 方式二 · 手动复制

把 `QuantumultX.conf` 内容整体复制，粘贴进 Quantumult X 的配置文件编辑器。

## 注意事项

### 1. 本仓库不含任何节点

`[server_local]` 与 `[server_remote]` **都是空的** —— 节点请自行添加。

这既是隐私考虑，也是一条底线：**任何情况下都不要把节点或订阅链接提交进本仓库**。
一旦提交，即使之后删除，git 历史里仍然翻得出来。

### 2. 地区组靠关键词匹配节点名

`德国节点` / `火鸡节点` 这类组是用 `server-tag-regex` 按关键词自动归集节点的，
例如德国组匹配 `德 / DE / Germany / Frankfurt / Berlin`。

**如果你的节点命名习惯不同，需要改对应的 `server-tag-regex`**，否则该组会是空的。

配置里每个组上方都有一行注释，写明它匹配哪些关键词。

### 3. 分不清「卡」是谁的锅

先跑一遍 `docs/圈X导入后验证清单.html`，里面有针对性排查步骤，
涵盖「某个 App 突然变卡」和「豆包专项」两种情况。

## 目录结构

```
ss_qx_plan/
├── QuantumultX.conf            主配置
├── README.md
├── docs/
│   ├── 圈X定制版使用说明.html
│   ├── 圈X规则总清单.html
│   ├── 圈X导入后验证清单.html
│   ├── 圈X体检与优化方案.html
│   └── 墨鱼2.0去广告清单与卡顿排查.html
└── icons/
    ├── 大马节点-方旗版.png
    ├── 大马节点-徽记版-备选.png
    └── 大马节点-改前改后对比.png
```

## 说明

个人自用配置，**不保证长期可用，也不承诺处理 issue**。

Quantumult X 的版本更新、各 App 的域名变化、远程规则集的新增改动，
都可能让某条规则失效。遇到问题请优先参考 `docs/` 里的文档自行排查。
