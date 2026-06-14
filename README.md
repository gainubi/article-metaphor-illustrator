# Article Metaphor Illustrator

[中文](README_ZH.md)

A Codex Skill that creates hand-drawn illustrations for Chinese articles.

Give Codex an article, a document link, or a selected passage. The Skill reads the content, finds where illustrations would help, develops the visual concept, and generates 16:9 images.

It can visualize workflows, architectures, comparisons, relationships, and structures. It can also create restrained conceptual illustrations for personal and emotional writing.

![Direct Codex workflow](examples/01-direct-codex-workflow.png)

## What It Does

1. Finds the strongest illustration points in articles, blog posts, and long-form writing
2. Turns workflows, architectures, comparisons, and relationships into hand-drawn explanatory visuals
3. Preserves concrete details and key metaphors from the source instead of producing generic illustrations
4. Uses a recurring orange-and-cream cat to keep the visual language consistent
5. Produces 16:9 images ready for articles, presentations, and internal documents

## Examples

### Technical Workflows

![One group, one project](examples/02-one-group-one-project.png)

### Business Processes

![Business data inspection](examples/04-business-data-inspection.png)

### Reasoning and Relationships

![Reasoning flow](examples/05-reasoning-flow.png)

### Personal Writing

![The last phone call](examples/03-last-phone-call.png)

![Stories keep growing](examples/06-story-keeps-growing.png)

## Usage

Give Codex an article, Word file, or readable document link, then say:

```text
Create illustrations for this article
```

You can also provide a single passage:

```text
Create one hand-drawn illustration for this passage
```

The Skill handles content analysis, placement selection, diagram routing, visual conception, and image generation.

## Installation

Send this repository URL to Codex:

```text
https://github.com/gainubi/article-metaphor-illustrator

Install this Skill for me
```

Codex will install it automatically. Restart Codex after the installation.

For manual installation, download the repository ZIP and extract it to `~/.codex/skills/article-metaphor-illustrator`.

## Customization

The default character reference is stored at `assets/orange-cat-main-visual.png`. You can replace it with your own animal character, company mascot, or personal avatar.

## Acknowledgements

The early concept was inspired by [Ian Xiaohei Illustrations](https://github.com/helloianneo/ian-xiaohei-illustrations).

## License

[MIT License](LICENSE)
