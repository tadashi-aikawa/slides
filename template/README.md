# template

スライドテンプレート用のプロジェクト。

## 起動

```bash
marp -s . --html
```

## スライド作成のヒント

### SVGアイコン

1. #000 のSVGアイコンをダウンロード
2. [css-color-filter-generator](https://angel-rs.github.io/css-color-filter-generator/) を使ってfilterを作成
3. 2のfilterをカスタムプロパティとして定義

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
