# template

スライドテンプレート用のプロジェクト。

## 起動

```bash
marp -s . --html
```
## ビルド

### HTML

```bash
marp index.md --html --theme style.css
```

### PDF

```bash
marp index.md --html --theme style.css --pdf --allow-local-files
```

### pptx

```bash
marp index.md --html --theme style.css --pptx --allow-local-files
```
