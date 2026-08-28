# photo-to-impasto

> 把任意照片变成可触摸的调色刀厚涂小品 —— 颜料真的鼓起来，光真的在颜料上走。

1:1 方形小品 | 3–5mm 厚涂隆起 | 方向性刀痕凹槽/凸脊 | 左上单一光源 | 暖象牙纸平面对比 | 黑手写歪扭标题

## 安装

```bash
npx skills add uyoujian/photo-to-impasto
# 或
openclaw skills install @uyoujian/photo-to-impasto
```

或直接复制 `SKILL.md` 到你的 `~/.agents/skills/photo-to-impasto/`

## 触发词

`照片转厚涂油画` `厚涂` `impasto` `调色刀` `油画小品` `照片转油画` `photo to oil painting`

## 用法

丢一张照片，说“转成厚涂油画”即可。Caption 按类型自动判断：

| 类型 | 标题 | 例 |
|---|---|---|
| 食物/饮品 | 菜单名 | Pancake / Peanut Cookies |
| 产品 | 品名 | Camera |
| 人物 | 短句 | A quiet afternoon |
| 动物 | 种类 | Ginger Cat |
| 风景 | 地名 | Jeju Sea |

## 效果

| 原图 | 厚涂小品 (Agnes Image 2.0 Flash, 1024×1024) |
|---|---|
| `lucky.png` (peach row) | `lucky-impasto-v03.png` (Peanut Cookies) |

四门检查：厚度/光影/纸张/文字 — 任一不过即重做

## 文件

```
photo-to-impasto/
├── SKILL.md
└── references/style-spec.md
```

## Source

Condensed from `01-内容生产/素材库/视觉风格/照片转厚涂油画风格提示词.md` → v0.31 English contract
