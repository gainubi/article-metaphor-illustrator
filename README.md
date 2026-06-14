# Article Metaphor Illustrator

一个面向中文文章的手绘配图 Skill。

它不会拿到文章就立刻写图片提示词，而是先理解全文、选择真正需要插图的位置、判断合适的图型，再生成 16:9 的极简强线条插图。

默认主视觉是一只橙白圆猫。你也可以替换成自己的动物形象、公司 IP 或个人卡通角色。

![告别来回复制](examples/01-direct-codex-workflow.png)

## 能做什么

这个 Skill 适合为以下内容生成正文插图：

1. 中文公众号文章、博客和长文
2. 技术文章中的流程、架构和关系
3. 方法论中的对比、结构和步骤
4. 感性文章中的关键场景与情绪收束
5. PPT、内部文档和知识库中的解释图

它支持六种主要图型：

1. 流程图
2. 架构图
3. 对比图
4. 关系图
5. 结构图
6. 概念插图

## 使用方式

安装完成后，把文章内容、Word 文件或可读取的文档链接交给 Codex，然后说：

```text
给这篇文章配图
```

也可以只提供一个段落：

```text
给这一段做一张手绘配图
```

如果你已经知道需要配图的位置，可以直接指定：

```text
给讲一个群就是一个项目的段落做一张配图
```

构思完成后会直接生成，不需要再次确认。需要先审阅方案时，可以明确说：

```text
先给我看配图构思，不要生成
```

## 安装

### 方法一：直接克隆

```bash
git clone https://github.com/gainubi/article-metaphor-illustrator.git \
  ~/.codex/skills/article-metaphor-illustrator
```

### 方法二：下载 ZIP

下载仓库 ZIP，将解压后的目录放到：

```text
~/.codex/skills/article-metaphor-illustrator
```

安装后重新启动 Codex，让它加载新的 Skill。

## 工作流程

整个过程分为六步：

```text
读取文章
  ↓
建立文章地图
  ↓
识别图型与插图位置
  ↓
完成构思卡
  ↓
验证可读性
  ↓
生成并检查图片
```

### 1. 建立文章地图

Skill 会提炼文章主命题、段落作用、情绪变化，以及文章独有的物件、动作和案例。

这些独特线索在 Skill 中被称为原文指纹。它们能避免图片虽然好看，却和文章没有直接关系。

### 2. 选择合适的图型

明确的步骤优先使用流程图，系统协作优先使用架构图，两个方案的差异使用对比图。

只有当重点是情绪、隐喻、案例或余味时，才使用概念插图。

### 3. 选择插图位置

Skill 不会平均地给每一部分配图，而是优先选择需要解释、区分、转折、记忆或收束的位置。

### 4. 完成构思卡

每张图只表达一个主要判断，并明确：

1. 单一命题
2. 原文指纹
3. 信息单位和组织方式
4. 阅读顺序
5. 重复元素预算
6. 视觉重量
7. 橙猫承担的动作
8. 手写中文标签

### 5. 验证构思

正式生成前会检查图片能否在一秒内看出主体、三秒内理解判断，以及它是否过于通用、依赖长文字或包含过多重复元素。

### 6. 生成和交付

最终生成 16:9 横向图片，并保存图片、插入位置、构思说明和提示词。

## 视觉风格

默认视觉规则：

1. 16:9 横向画幅
2. 奶白色背景
3. 简约、有力的黑色手绘线条
4. 大量留白
5. 小面积暖橙色点睛
6. 少量手写中文短标签
7. 避免规则网格和重复卡片造成的 PPT 感

文字颜色承担语义：

1. 黑色表示对象名称和普通状态
2. 橙色表示主路径、关键动作和核心节点
3. 红色表示问题、阻塞和风险
4. 蓝色表示外部条件和次要补充

## 示例

### 一个群，一个项目

![一个群一个项目](examples/02-one-group-one-project.png)

### 最后一通电话

![最后一通电话](examples/03-last-phone-call.png)

同一个 Skill 可以处理技术解释图，也可以处理更克制的情绪插图。

## 替换角色

默认角色参考图位于：

```text
assets/orange-cat-main-visual.png
```

替换图片后，需要同步修改以下文件中的角色描述：

```text
SKILL.md
references/conception-protocol.md
references/prompt-templates.md
references/visual-translation.md
```

角色应参与画面的关键动作，而不是只站在角落里作为装饰。

## 目录结构

```text
article-metaphor-illustrator/
├── SKILL.md
├── assets/
│   ├── README.md
│   └── orange-cat-main-visual.png
├── examples/
├── references/
│   ├── annotation-system.md
│   ├── conception-protocol.md
│   ├── diagram-types.md
│   ├── prompt-templates.md
│   └── visual-translation.md
├── LICENSE
└── THIRD_PARTY_NOTICES.md
```

## 设计来源

这个项目在早期探索中受到 [Ian Xiaohei Illustrations](https://github.com/helloianneo/ian-xiaohei-illustrations) 启发。

在此基础上，本项目重新设计并扩展了文章地图、图型路由、原文指纹、构思卡、可读性验证、重复元素预算、视觉重量和手写标注系统。

详细说明见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。

## License

[MIT License](LICENSE)
