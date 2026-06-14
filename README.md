# Article Metaphor Illustrator

一个为中文文章生成手绘配图的 Codex Skill。

把文章、文档链接或其中一段发给 Codex，它会理解内容，找到适合配图的位置，完成构思并生成 16:9 横向插图。

它既能画流程、架构、对比、关系和结构，也能为感性文章生成更克制的概念插图。

![告别来回复制](examples/01-direct-codex-workflow.png)

## 能做什么

1. 为公众号文章、博客和长文选择配图位置
2. 把流程、架构、对比和关系画成手绘解释图
3. 提取文章里的具体案例和关键意象，避免生成与原文无关的通用图片
4. 使用固定橙白圆猫保持整套图片的视觉一致性
5. 输出可直接用于文章、PPT 和内部文档的 16:9 图片

## 效果示例

### 技术与工作流

![一个群一个项目](examples/02-one-group-one-project.png)

### 感性文章

![最后一通电话](examples/03-last-phone-call.png)

## 使用

把文章内容、Word 文件或可读取的文档链接交给 Codex，然后说：

```text
给这篇文章配图
```

也可以只给一个段落：

```text
给这一段做一张手绘配图
```

Skill 会依次完成文章理解、位置选择、图型判断、画面构思和图片生成。

## 安装

```bash
git clone https://github.com/gainubi/article-metaphor-illustrator.git \
  ~/.codex/skills/article-metaphor-illustrator
```

安装完成后重新启动 Codex。

也可以下载仓库 ZIP，解压到：

```text
~/.codex/skills/article-metaphor-illustrator
```

## 自定义

默认角色位于 `assets/orange-cat-main-visual.png`。可以替换成自己的动物形象、公司 IP 或个人卡通角色。

## 致谢

项目的早期思路受到 [Ian Xiaohei Illustrations](https://github.com/helloianneo/ian-xiaohei-illustrations) 启发。

## License

[MIT License](LICENSE)
