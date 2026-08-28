# Photo to Impasto — Style Spec (v0.31)

Source: `01-内容生产/素材库/视觉风格/照片转厚涂油画风格提示词.md` (condensed to v0.31 English contract)
Use for: 公众号封面插图、小红书配图、个人作品 via Agnes Image 2.0 Flash / GPT-Image / Flux 等图生图模型

## Prompt contract (v0.31 — canonical, absorbs Chinese spec)

```
1:1 square canvas, palette-knife impasto oil painting miniature, heavy thick raised paint 3-5mm, distinct directional grooves and ridges per paint lump, top-left single light source, strong highlight on raised ridges, deep shadow in recesses and stacked layers, subtle edge shadow so color masses stack on different layers, follow original silhouette, palette and composition, simplified block-shaped forms with restrained density (few bold strokes still recognizable), no over-detailing.
Background: flat warm-ivory textured paper, subtle fine grain only, flat to contrast dimensional subject, NO border, NO black outline, NO frame, clean wide margin of empty paper around subject.
Bottom corner: natural crooked black hand-written caption text "[Caption]" — auto by type (food→menu name like Pancake, product→name, person→short phrase, animal→species, landscape→place), hand-drawn script, neat printed font forbidden, no extra decorations.
Composition: subject ([subject description]) centered in canvas, single cohesive cluster, generous empty margin, keep [layout] layout, no extra props.
Forbidden: watercolor wash, transparent layers, soft color blending, gradient, photorealism, glossy finish, airbrush, black border, frame, outline, extra text.
```

## Core instruction

将附件照片中的主体转换为调色刀厚涂油画风格的方形小品画（1:1）。

## Style — 强调立体感（中文 spec 精炼，已吸入 Prompt）

- 用调色刀将颜料厚厚堆叠，大胆到表面凸起3~5mm的程度（厚涂法 impasto）→ 已进 Prompt 首句
- 每一团颜料的笔触方向性要清晰保留（调色刀经过的凹槽与凸脊）→ `per paint lump grooves and ridges`
- 假设光源从左上方照射：凸起颜料部分要有明亮的高光，凹陷或叠压部分要有清晰阴影 → `top-left single light, highlight on ridges, deep shadow in recesses and stacked layers`
- 颜料边缘带微弱阴影，让各色团看起来像在不同图层上层叠堆积（避免平面感）→ `subtle edge shadow so color masses stack`
- 主体的轮廓、色感、构图跟随原片，但不追求写实渲染，而是用厚颜料团块简化形体 → `follow original silhouette, palette and composition, simplified block forms`
- 不要过度精细，仅用几道粗犷立体的刀触就能辨认形体的克制密度 → `restrained density (few bold strokes still recognizable)`

## Background

- 固定为带轻微颗粒纹理的暖色象牙/奶油色纸背景，平面感，与主体立体对比
- 无边框、无黑线、无画框，留足干净纸张余白

## Text

- 在背景底部（或留白最宽的一侧）角落，插入黑色手写体标题，文字颜色固定为黑色
- 文案根据照片主体自动判断生成：
  - 食物/饮品 → 菜单名（如 Pancake, Earl grey cake / Peanut Cookies）
  - 产品 → 产品名或品类名
  - 人物 → 表达此人的短句或名字感文本
  - 动物 → 动物名称或种类
  - 风景 → 地点名或风景对应的短词
- 手写体要自然歪扭有书写感，不要像字体一样整齐，无额外装饰

## Ratio / Composition

- 输出比例固定1:1
- 主体居中，留足余白，无装饰小物，只放一个主体（多主体时收为一个 cohesive cluster，保持原水平/居中布局）

## Avoid (黑名单 — 触发即重做)

watercolor wash, transparent layers, soft color blending, gradient, photorealism, glossy finish, airbrush, black border, frame, outline, extra text

## 四门检查（任一不过即重做）

1. 厚度门：侧光下可见 3-5mm 隆起与方向性刀痕 ridges/grooves
2. 光影门：左上单一光源，高光 vs 谷底阴影分明
3. 纸张门：暖象牙纸平坦，仅微颗粒，无水渍晕染，无边框
4. 文字门：黑手写仅一处，歪扭，不糊，无打印字体

## Model notes

- API size: `1024x1024` (square). For other models use 1:1 equivalent.
- Always pass source photo as image reference / edit input.
- Text rendering in image models is unreliable — if caption is garbled, regenerate with `caption: "EXACT TEXT"` emphasized, or add text in post-processing.
