---
theme: mamansoft
_class: lead
paginate: true
---

<script src="https://cdn.tailwindcss.com/3.4.4"></script>
<script>tailwind.config = { corePlugins: { preflight: false } }</script>

# テンプレート

##### yyyy-mm-dd title

tadashi-aikawa

---

![bg left:30%](https://publish-01.obsidian.md/access/35d05cd1bf5cc500e11cc8ba57daaf88/Notes/attachments/Pasted%20image%2020210605212644.png)

<div>
  <h1 class="text-foreground">Tadashi Aikawa</h1>
  <h5 class="text-dimmed">Productivity Creator since 2010</h5>
  <div class="mt-12 space-y-2 text-2xl">
    <div>
      <div class="label">OS</div>
      <span class="pl-3">Windows <small>(開発はUbuntu on WSL)</small></span>
    </div>
    <div>
      <div class="label">言語</div>
      <span class="pl-3">TypeScript >> Python = Go = Rust >> Lua</span>
    </div>
    <div>
      <div class="label">エディタ</div>
      <span class="pl-3">Neovim / Obsidian</span>
    </div>
    <div>
      <div class="label">デバイス</div>
      <span class="pl-3">EIZO / HHKB Studio / SlimBlade</span>
    </div>
    <div>
      <div class="label">サイト</div>
      <a class="pl-3" href="https://minerva.mamansoft.net/">Minerva</a>
      <a class="pl-3" href="https://github.com/tadashi-aikawa">GitHub</a>
      <a class="pl-3" href="https://bsky.app/profile/tadashi-aikawa.bsky.social">
        Bluesky
      </a>
    </div>
    <div>
      <div class="label">好き</div>
      <span class="pl-3">創作活動・温泉・甘味・動物(ぬいぐるみ含む)</span>
    </div>
    <div>
      <div class="label">苦手</div>
      <span class="pl-3">お酒・車・勉強</span>
    </div>
    <div>
      <div class="label">楽しい仕事</div>
      <span class="pl-3">個人やチームの生産性を上げて成果に繋げる</span>
    </div>
  </div>
</div>

<!-- 仕事だったら『所属』『代表プロダクト』『入社年』などを入れる -->

---

<!-- _class: chapter-divider -->

<div class="left">

### Agenda

</div>

<div class="right">

1. はじめに
2. 基本的な装飾
3. レイアウトテンプレート
4. スライドテンプレート
5. まとめ

</div>

---

<!-- _class: chapter-divider -->

<div class="left">

### Chapter

## 01

</div>

<div class="right">

1. **はじめに**
2. 基本的な装飾
3. レイアウトテンプレート
4. スライドテンプレート
5. まとめ

</div>

---

## このスライドを作成した目的

- スライド作成スピードを上げたい
- デザインを安定させたい
- 極力Markdownでスライドを作りたい
- デザイン/CSSのスキルを向上させたい

---

<!-- _class: chapter-divider -->

<div class="left">

### Chapter

## 02

</div>

<div class="right">

1. ~~はじめに~~
2. **基本的な装飾**
3. レイアウトテンプレート
4. スライドテンプレート
5. まとめ

</div>

---

## 見出し

<div class="grid-col-3-7">

# LEVEL1
`# LEVEL1`
</div>

<div class="grid-col-3-7">

## LEVEL2
`## LEVEL2`
</div>

<div class="grid-col-3-7">

### LEVEL3
`### LEVEL3`
</div>

<div class="grid-col-3-7">

#### LEVEL4
`#### LEVEL4`
</div>

<div class="grid-col-3-7">

##### LEVEL5
`##### LEVEL5`
</div>

<div class="grid-col-3-7">

###### LEVEL6
`###### LEVEL6`
</div>



---

## インライン装飾

| ユースケース           | raw          | 表示       |
|------------------------|--------------|------------|
| 強調したいとき         | `**strong**` | **strong** |
| 強く強調したいとき     | `_emphasis_` | _emphasis_ |
| 注意をひきたくないとき | `~~mute~~`   | ~~mute~~   |
| リンク入りテキスト     | `[Marp]`     | [Marp]     |

---

<!-- _class: grid-5-5 -->

## ブロック装飾

- 箇条書き
  - ネストにも対応
- LEVEL1
  - LEVEL2
    - LEVEL3
      - LEVEL4
        - は続くよどこまでも...
- 推奨はLEVEL1のみ
  - どうしても必要な場合のみLEVEL2

1. 番号付きリスト
1. 数値は
1. Incrementされて
1. 順番にふられます
1. ネストには未対応

---

## コードブロック

```lua
return {
  dir = "~/git/github.com/tadashi-aikawa/ghostwriter.nvim",
  dependencies = {
    "nvim-lua/plenary.nvim",
  },
  keys = {
    { "<C-j>m", ":Ghostwrite<CR>", silent = true },
  },
  config = function()
    require("ghostwriter").setup({
      check = {
        { mark = "~", emoji = "loading" },
        { mark = "x", emoji = "ok_green" },
        { mark = "_", emoji = "rip" },
        { mark = "-", emoji = "togowl_pause" },
        { mark = " ", emoji = "circle-success" },
      },
      bullet = {
        emoji = "diamond_shape_with_a_dot_inside",
      },
    })
  end,
}
```

---

<!-- _class: chapter-divider -->

<div class="left">

### Chapter

## 03

</div>

<div class="right">

1. ~~はじめに~~
2. ~~基本的な装飾~~
3. **レイアウトテンプレート**
4. スライドテンプレート
5. まとめ

</div>

---

## directiveに使うclass

| クラス名               | 用途                           |
|------------------------|--------------------------------|
| lead                   | 中央寄せ                       |
| full                   | 四隅のパディングやマージンなし |
| narration-white        | 白文字のナレーションを中央に   |
| text-dimmed-background | 暗転背景にテキスト             |
| borderless-table       | 線のないテーブル               |
| headless-table         | ヘッダのないテーブル           |

---

<!-- _class: chapter-divider -->

<div class="left">

### Chapter

## 04

</div>

<div class="right">

1. ~~はじめに~~
2. ~~基本的な装飾~~
3. ~~レイアウトテンプレート~~
4. **スライドテンプレート**
5. まとめ

</div>

---

<!-- _class: lead -->

## 画面中央で

### 語るスライド

---

## 画像のセンタリング

![neovim-girl center w:960](https://publish-01.obsidian.md/access/35d05cd1bf5cc500e11cc8ba57daaf88/Notes/attachments/neovim-girl-1280.webp)

---

## 画像のドロップシャドー

![neovim-girl drop-shadow center w:960](https://publish-01.obsidian.md/access/35d05cd1bf5cc500e11cc8ba57daaf88/%F0%9F%93%B0Weekly%20Report/attachments/Pasted%20image%2020240812132709.png)

---

<!-- _class: full lead -->

![bg neovim-girl](https://publish-01.obsidian.md/access/35d05cd1bf5cc500e11cc8ba57daaf88/Notes/attachments/neovim-girl-1280.webp)

<div class="tag-note">画像をスライド全体に表示</div>

---

<!-- _class: full lead narration-white -->

中央に
黒い半透明背景で
白文字を出したいとき

![bg neovim-girl](https://publish-01.obsidian.md/access/35d05cd1bf5cc500e11cc8ba57daaf88/Notes/attachments/neovim-girl-1280.webp)

---

<!-- _class: full lead text-dimmed-background -->

## 画像を黒く暗転して
## 白文字を出したいとき

![bg brightness:0.25 neovim-girl](https://publish-01.obsidian.md/access/35d05cd1bf5cc500e11cc8ba57daaf88/Notes/attachments/neovim-girl-1280.webp)

---

<!-- _class: lead -->

> もともと私はアンチVimだった。なぜなら、AutoHotkeyを使ってOSレベルで効率的なキーバインドを実現していたからだ。その全容は🦉Spinal reflex bindings templateというリポジトリで管理している。
> 
> 🦉Spinal reflex bindings templateの設計思想はVimのモードに近しいものがある。だからこそ、それに満足しており、苦労してまでVimを覚える気にはなれなかったのだ。
> 
> ところが、このときの私は大きな誤解をしていた。**_私が分かったつもりでいたVimの思想は氷山の一角に過ぎなかったのである_**。
> 
> それに気付かせてくれた名著こそが📚実践Vimだ。📚実践Vimを読んで、私ははじめてVimの思想が何たるかを理解することができた。
> [📗Vimの思想を取り入れる \- Minerva](https://minerva.mamansoft.net/%F0%9F%93%97Productivity%E3%82%92%E4%B8%8A%E3%81%92%E3%82%8B%E3%81%9F%E3%82%81%E3%81%AB%E5%A4%A7%E5%88%87%E3%81%AA100%E3%81%AE%E3%81%93%E3%81%A8/%F0%9F%93%97Vim%E3%81%AE%E6%80%9D%E6%83%B3%E3%82%92%E5%8F%96%E3%82%8A%E5%85%A5%E3%82%8C%E3%82%8B)

<div class="tag-note">画面中央で引用を紹介</div>

---

<!-- _class: chapter-divider -->

<div class="left">

### Chapter

## 05

</div>

<div class="right">

1. ~~はじめに~~
2. ~~基本的な装飾~~
3. ~~レイアウトテンプレート~~
4. ~~スライドテンプレート~~
5. **まとめ**

</div>

---

## まとめ

- Marpを使うとMarkdownでスライドを作成できる
- Neovimで編集できるからスピーディーで快適
- 良いスライドを作るにはCSSの知識が必須
- CSSはその場しのぎではなく学びの機会として捉える
- 可能な限りHTMLを使わずにレイアウトする
- テンプレスライドを作っておくと一貫性が出るし楽
- レイアウトが実現できないときはスライド構成に疑問をもつ
- スライドはできるだけサイトとしてデプロイする

<!--
paginate: false
backgroundImage: url("https://publish-01.obsidian.md/access/35d05cd1bf5cc500e11cc8ba57daaf88/Attachments/mimizou-momochi.gif")
_backgroundSize: 100px
_backgroundPosition: right bottom
-->


[Marp]: https://marp.app/
