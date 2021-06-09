# Presentations

Generate HTML slides from markdown files using [cleaver](https://github.com/jdan/cleaver).

## Install Cleaver

```bash
npm i -g cleaver
```

## Markdown requirements

1. Include this options block at the beggining of markdown file.
  ```
  title: <TITLE>
  author:
    name: <NAME>
  output: <OUTPUT>.html
  controls: true

  --

  ```

2. Use `--` lines to separte slides.

## Generate slides

```bash
cleaver /path/to/markdown.md

# In watch mode
cleaver watch /path/to/markdown.md
```

Information on options/themes at https://github.com/jdan/cleaver
