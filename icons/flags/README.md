# 国家图标补充包 · 24 国

方版国家/地区图标，**108×108 PNG**，可直接用于 Quantumult X 策略组的 `img-url=`。

## 为什么有这一包

[Orz-3/mini](https://github.com/Orz-3/mini) 的图标库（Color 目录 336 个图标）里，
国家/地区类只有 17 个：

```
AU  CA  CN  DE  FR  HK  JP  KR  RU  SG  TH  TR  TW  UK  UN  US  VN
```

南美、中美、加勒比、欧洲小国基本是空白 —— 想给「巴西节点」「冰岛节点」配图标时
根本找不到同规格的，混着用风格会明显不统一。这里补齐 **24 个**。

## 清单

| 组 | 代码 |
| --- | --- |
| 南美 12 | `AR` 阿根廷 · `BO` 玻利维亚 · `BR` 巴西 · `CL` 智利 · `CO` 哥伦比亚 · `EC` 厄瓜多尔 · `GY` 圭亚那 · `PY` 巴拉圭 · `PE` 秘鲁 · `SR` 苏里南 · `UY` 乌拉圭 · `VE` 委内瑞拉 |
| 中美 / 加勒比 4 | `PA` 巴拿马 · `CR` 哥斯达黎加 · `GT` 危地马拉 · `CU` 古巴 |
| 欧洲小国 / 微型国 8 | `AD` 安道尔 · `MC` 摩纳哥 · `LI` 列支敦士登 · `SM` 圣马力诺 · `MT` 马耳他 · `LU` 卢森堡 · `IS` 冰岛 · `VA` 梵蒂冈 |

![预览](_preview-24-countries.png)

预览图第一行是 Orz-3 原版（现在地区组在用的规格），下面三行是新补的 —— 放在一起看风格是一致的。

## 规格

| 项 | 值 |
| --- | --- |
| 画布 | 108 × 108 px，PNG-32（带 alpha） |
| 可见区域 | 106 × 106（与 Orz-3 同规格） |
| 光泽 | 左上 → 右下的中性灰对角渐变，拟合自 Orz-3 原图 |
| 外轮廓 | 取自 Orz-3 图标，内部镂空已逐行填实（无横穿缝隙） |
| 超采样 | 432 × 432 渲染后降采样到 108，边缘干净 |

## 怎么用

```ini
[policy]
static=巴西节点, img-url=https://raw.githubusercontent.com/peqw0312/ss_qx_plan/main/icons/flags/BR.png, 节点1, 节点2
```

把 `BR.png` 换成对应的两位国家代码即可。

⚠️ Quantumult X 的 `img-url=` **只接受公网 HTTP(S) 地址**，不能填本地路径或相对路径 ——
所以放在 GitHub 上正好，本地文件是喂不进去的。

国内直连 `raw.githubusercontent.com` 可能失败，可加加速前缀：

```ini
img-url=https://ghproxy.net/https://raw.githubusercontent.com/peqw0312/ss_qx_plan/main/icons/flags/BR.png
```

## 来源与许可

国旗底图取自 [lipis/flag-icons](https://github.com/lipis/flag-icons) 的 `flags/1x1/`
（正方形适配版），**MIT 许可**。本目录下的 PNG 由它经浏览器无头渲染 + 后处理生成，
**可自由取用、修改、再分发，无需署名**。

需要别的国家？底图和生成脚本都在，加一行国家代码重跑一遍即可。
