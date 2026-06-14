# 提示词模板

提示词分两层：**风格基线**（每张图固定不变）+ **构思卡转译**（按已经确认的构思填写）。提示词不得脱离构思卡临时增加第二个观点。原文指纹必须出现在第一句，避免图片模型把它当成次要元素省略。

## 风格基线（固定，英文）

```
Minimalist bold-line hand-drawn editorial illustration, strong confident black ink contours with expressive variation in line weight, slightly organic hand-drawn edges, sparse thin interior detail lines, every object described with as few lines as possible, large areas of clean negative space, cream-white paper background, mostly monochrome black ink with one small warm accent color only, crisp readable silhouettes, clear information hierarchy, no watercolor wash, no pencil shading, no hatching, no heavy paper grain, no complex texture, no watermark, no border
```

概念插图追加：

```
no text, no letters, no words
```

包含流程、架构、对比、关系或结构时追加：

```
communicate through shapes, icons, alignment and connectors, no text unless a short label is explicitly required
```

## 画面描述模板（每张图填写）

按这个顺序写，每项一两个短语，总长控制在四五行以内。图片模型对前面的词权重更高，所以主体永远放最前面：

```
[主体 + 姿态]: the recurring orange-and-cream round cat mascot performing the article-specific action
[固定角色外形]: extremely round squat body, orange head and back, cream-white muzzle cheeks belly and front paws, small triangular ears, tiny black oval eyes and small black nose
[原文指纹]: the specific object, action, or domain detail that links the image to the article
[图型]: process diagram, architecture diagram, comparison diagram, relationship diagram, structure diagram, or conceptual illustration
[画幅]: strict 16:9 landscape composition, not 3:2, not square, not portrait
[单一命题]: the one conclusion the viewer should understand
[信息单位]: states, modules, comparison dimensions, relationship objects, components, or one visual subject
[组织规则]: sequence, layers, side-by-side comparison, network links, containment, or one conceptual relationship grammar
[重复元素预算]: maximum repeated elements and how additional items are grouped or abstracted
[视觉重量]: approximate canvas share of each main structure, no ordinary module above 15 percent and no core module above 20 percent
[手写中文标签]: 2 to 5 short handwritten Chinese labels, preferably 2 to 4 characters each, placed beside their objects
[标签语义]: black for object names, orange for main path, red for problems, blue for secondary context; use black plus only one functional color by default
[变化线]: the path, distance, split, size change, overlap, or direction that carries the relationship
[阅读顺序]: first see X, then follow Y, finally understand Z
[对照物]: one secondary object only if necessary
[构图与留白]: subject placed in lower-left, the rest of the canvas left empty
[角色比例]: the cat occupies only 6 to 10 percent of the canvas and serves as a scale reference
[线条层级]: strong outer contours, thinner interior detail lines, no repeated sketch strokes
[光线与色调]: implied warm daylight through sparse lines and open space, mostly monochrome
[主色点缀]: one small warm orange accent only
[情绪词]: quiet, suspended, facing forward
```

实际提交时把方括号去掉，连成逗号分隔的一段，再接风格基线。

写完提示词后，对照构思卡检查：

1. 是否出现构思卡中没有的新物件？
2. 是否把一个关系语法变成了多个并列关系？
3. 第一眼主语是否仍然只有一个？
4. 橙猫动作是否仍然服务于单一命题？
5. 图型是否与构思卡一致？
6. 是否明确写入 strict 16:9 landscape composition？
7. 是否把超过预算的相似对象合并成集合、重叠轮廓、密度或阶段？
8. 是否限制了单个模块的面积和细节重量？
9. 是否列出了需要准确生成的手写中文标签？
10. 标签颜色是否服务语义而不是装饰？

任一答案不符合，先改提示词，不要直接生成。

包含结构型内容时统一追加：

```text
Avoid mechanical repetition. Show no more than three large near-identical objects and no more than five small repeated marks. Group additional items into one cluster, stacked outline, density band, or representative object. Consistency comes from shared line language and alignment, not from copying many identical icons.
Maintain balanced visual weight. No ordinary module should occupy more than 15 percent of the canvas and no core module more than 20 percent. Do not combine oversized scale, thick outline, dense internal detail and strong orange fill on the same object.
The complete core composition should occupy roughly 40 to 60 percent of the canvas. Avoid a PowerPoint-like grid, repeated rounded boxes, uniform arrows, and any diagram-type title in the upper-left.
```

需要标签时追加：

```text
Include only these exact short Chinese labels in a clear natural handwritten style: [逐项列出]. Each label stays close to its object. No additional text. Render every Chinese character exactly as provided.
```

标签颜色按构思卡写明，不自动使用多色。默认黑色标签加一种功能色。

## 图型专用骨架

### 流程图

```text
Diagram type: process diagram
Start state: [...]
Ordered nodes: [...] -> [...] -> [...]
End state: [...]
Optional single feedback loop: [...]
Reading direction: left to right
Node consistency: same shape and size, one orange key node
```

### 架构图

```text
Diagram type: architecture diagram
System boundary: [...]
Input: [...]
Core modules or layers: [...]
Primary data flow: [...]
Output: [...]
Layout: left-center-right or top-middle-bottom, choose one
```

### 对比图

```text
Diagram type: comparison diagram
Shared input or question: [...]
Left approach: [...]
Right approach: [...]
Comparison dimensions: [...]
Different outcomes: [...]
Layout: strict mirrored alignment
```

### 关系图

```text
Diagram type: relationship diagram
Core object: [...]
Related objects: [...]
Relationship direction: [...]
Relationship type or strength: [...]
Layout: one clear center or one clean network, no line crossing
```

### 结构图

```text
Diagram type: structure diagram
Whole object or system: [...]
First-level components: [...]
Containment or layer rule: [...]
Optional second-level detail: [...]
Layout: cutaway, nested containers, or layers, choose one
```

橙猫不是必需节点。只有它能执行关键动作、指出入口或提供尺度时才使用。

提示词第一句建议使用这个结构：

```
The central recognizable article anchor is [原文指纹], clearly visible and not omitted.
```

如果是科技、商业或产品文章，优先写清楚对象的外观和操作关系，不要只写 technology、competition、progress 这类抽象词。

生成前读取 `assets/orange-cat-main-visual.png` 并把它作为角色参考图。提示词中加入：

```
Use the provided orange cat image as the strict character reference. Preserve its extremely round squat body, orange head and back, cream-white muzzle cheeks belly and front paws, small triangular ears, tiny black oval eyes, small black nose and gentle slightly goofy expression. Adapt only the pose and action. Render it in the illustration's bold minimal line style rather than copying the thick painted texture.
```

## 完整示例

```
A tiny figure seen from behind sitting at the bow of a small boat, calm water suggested by three long horizontal lines, vast empty space ahead, subject in lower-left, strong outer contours and sparse thin interior lines, one small warm orange scarf, quiet and forward-facing mood. Minimalist bold-line hand-drawn editorial illustration, strong confident black ink contours with expressive variation in line weight, slightly organic hand-drawn edges, every object described with as few lines as possible, large areas of clean negative space, cream-white paper background, mostly monochrome black ink with one small warm accent color only, crisp readable silhouette, simple poetic composition, no watercolor wash, no pencil shading, no hatching, no heavy paper grain, no complex texture, no text, no letters, no words, no watermark, no border
```

## 中文版基线（给国产模型用，如即梦、可灵、Mavis）

```
极简强线条手绘插画，使用明确有力的黑色墨线轮廓，线条粗细有表现力，轮廓略粗、内部细节线更细，每个物体尽量用最少的线条表达，画面留白超过一半，奶白色纸张底色，以黑色线稿为主，全画只保留一处小面积暖色点睛，轮廓清楚，构图简洁有诗意，不要水彩铺色，不要铅笔涂抹，不要排线阴影，不要明显纸张颗粒，不要复杂纹理，画面中不出现任何文字、字母、水印、边框
```

中文画面描述同样遵循"主体在前"的顺序，与中文基线拼接。

## 负面提示词（如工具支持单独填写）

```
text, letters, words, typography, watermark, signature, border, frame, photorealistic, 3D render, watercolor wash, painterly fill, pencil shading, cross-hatching, dense sketch strokes, repeated outlines, heavy paper grain, complex texture, oversaturated colors, neon colors, busy background, realistic cat, shiba inu, fox, bear, thin cat, long-legged cat, ordinary cartoon cat, changed orange-and-cream markings
```

## 参数建议

- 所有文章正文配图固定使用 16:9 横向画幅
- 推荐尺寸：1536 × 864，或其他严格 16:9 尺寸
- 不允许因为概念插图、留白或角色构图改用 3:2
- 只有用户明确指定其他比例，或任务明确是公众号封面时才例外
- 每个画面出 2 张备选
- 如有"风格强度 / stylize"参数，取中等，避免模型添加过多装饰纹理

## 常见翻车与修正

| 问题 | 修正 |
|---|---|
| 概念插图出现乱码文字 | 把 no text 系列负词前移，或删掉可能被理解为标牌、书本、屏幕的元素 |
| 手写短标签错误 | 优先改为无文字图形表达；必须保留时缩短标签并逐字检查 |
| 流程图像一排装饰图标 | 明确起点、状态变化、方向和终点，统一节点形状 |
| 架构图像流程图 | 增加系统边界和模块层级，数据流只作为连接，不把所有模块排成步骤 |
| 对比图两边无法比较 | 使用相同数量、位置和尺度的视觉单位，只保留共同维度 |
| 关系线太乱 | 减少对象，重排布局，线条交叉超过两处就重构 |
| 结构图像漂浮图标 | 增加整体边界和包含关系，使用剖面、容器或单一分层 |
| 输出画面偏高 | 在提示词开头和结尾都强调 "strict 16:9 landscape composition, not 3:2, not square, not portrait"，并检查实际像素比例 |
| 相同卡片或模块太多，像模板拼装 | 将多余对象合并成集合、重叠轮廓、密度带或阶段容器；大型同形元素最多 3 个 |
| 节点统一但画面单调 | 保持外框语言一致，同时让内部图形、留白比例和轮廓节奏服务不同含义 |
| 单个漏斗或模块太大，压住全图 | 限制普通模块不超过 15%，核心模块不超过 20%；缩小体量并减少内部细节 |
| 对比图一边明显更重 | 对齐两侧外接面积，复杂一侧减少细节或缩小，简单一侧增加必要轮廓 |
| 中文标签错误或像印刷标题 | 标签缩短到 2 至 4 字，明确逐字内容和手写风格，生成后逐字校对 |
| 线条太细太弱 | 加强 "strong confident black ink contours, bold readable silhouette, expressive line-weight variation" |
| 画面像草稿，线条反复 | 加入 "single decisive contour lines, no repeated outlines, no dense sketch strokes" |
| 出现水彩晕染或复杂纹理 | 加入 "no watercolor wash, no painterly fill, no pencil shading, no hatching, no heavy paper grain" |
| 角色变成普通猫或其他动物 | 重新读取参考图，加强固定体型、橙白分区、小耳朵和面部特征，并加入 realistic cat, shiba inu, fox, thin cat 等负词 |
| 角色太大，压过文章意象 | 加入 "the cat occupies only 6 to 10 percent of the canvas, scale reference rather than focal point"，并把角色放在角落或路径起点 |
| 角色过度卖萌 | 强调 "gentle slightly goofy expression, restrained editorial mood, action serves the article, not a cute sticker" |
| 颜色太多，削弱线稿 | 强调 "mostly monochrome black ink with one small warm accent color only" |
| 画面太满没有留白 | 画面描述里给留白指定具体方位，如 "upper two thirds left empty" |
| 风格很好但看不出和文章的关系 | 把原文指纹移到第一句，具体描述其形状、动作和位置，并删掉一个通用象征物 |
| 原文指纹被模型省略 | 加入 "central recognizable article anchor, clearly visible and not omitted"，减少次要元素 |
| 像产品截图，缺少情绪 | 保留技术对象，但用比例、远近、留白、光线和材质表达文章的关系与态度 |
