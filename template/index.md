---
theme: mamansoft
_class: lead
---

<script src="https://cdn.tailwindcss.com/3.4.4"></script>
<script>tailwind.config = { corePlugins: { preflight: false } }</script>

# テンプレート

##### yyyy-mm-dd title

tadashi-aikawa

---

<!-- _class: full side-3-7 side-no-title -->

<div class="bg-primary">
  <h2>01</h2>
</div>

<div>hoge</div>

---

<!-- _class: full side-3-7 side-no-title -->

<div class="flex justify-center items-center">
  <img src="https://publish-01.obsidian.md/access/35d05cd1bf5cc500e11cc8ba57daaf88/Notes/attachments/Pasted%20image%2020210605212644.png" height="100%" />
</div>

<div class="py-12">
  <h1 class="text-foreground">Tadashi Aikawa</h1>
  <h5 class="text-dimmed">Productivity Creator since 2010</h5>
  <div class="mt-12 space-y-2 text-2xl">
    <div>
      <code class="w-48 text-center">OS</code>
      <span class="pl-2">Windows <small>(開発はUbuntu on WSL)</small></span>
    </div>
    <div>
      <code class="w-48 text-center">言語</code>
      <span class="pl-2">TypeScript >> Python = Go = Rust >> Lua</span>
    </div>
    <div>
      <code class="w-48 text-center">エディタ</code>
      <span class="pl-2">Neovim / Obsidian</span>
    </div>
    <div>
      <code class="w-48 text-center">デバイス</code>
      <span class="pl-2">EIZO / HHKB Studio / SlimBlade</span>
    </div>
    <div>
      <code class="w-48 text-center">サイト</code>
      <a class="pl-2" href="https://minerva.mamansoft.net/">Minerva</a>
      <a class="pl-2" href="https://github.com/tadashi-aikawa">GitHub</a>
      <a class="pl-2" href="https://bsky.app/profile/tadashi-aikawa.bsky.social">
        Bluesky
      </a>
    </div>
    <div>
      <code class="w-48 text-center">好き</code>
      <span class="pl-2">創作活動・温泉・甘味・動物(ぬいぐるみ含む)</span>
    </div>
    <div>
      <code class="w-48 text-center">苦手</code>
      <span class="pl-2">お酒・車・勉強</span>
    </div>
    <div>
      <code class="w-48 text-center">楽しい仕事</code>
      <span class="pl-2">個人やチームの生産性を上げて成果に繋げる</span>
    </div>
  </div>
</div>

<!-- 仕事だったら『所属』『代表プロダクト』『入社年』などを入れる -->

---

## アジェンダ

1. テーマ1
2. テーマ2
3. テーマ3
4. テーマ4
5. まとめ

---

## アジェンダ

1. **テーマ1**
2. ~~テーマ2~~
3. ~~テーマ3~~
4. ~~テーマ4~~
5. ~~まとめ~~

---

## アジェンダ

1. ~~テーマ1~~
2. **テーマ2**
3. ~~テーマ3~~
4. ~~テーマ4~~
5. ~~まとめ~~

---

## メッセージ

ここに普通にメッセージを書く想定です。そのあとに...

- hoge
- hoge
- hoge

---

## 基本的な装飾

- **太字**
- **<em>強調色</em>をつかって**<em>強調する</em>
- `inline code`
- ~~とりけし~~線は目立たない色

---

<!-- _class: grid-5-5 -->

## grid-layout

<div>

- hugahuga
- <img src="https://publish-01.obsidian.md/access/35d05cd1bf5cc500e11cc8ba57daaf88/favicon-64.png" />

  - hogehoge
- huga
</div>

```ts
const hoge = "hoge"
```

---

## 利用できるclass

| クラス名               | 用途                           |
|------------------------|--------------------------------|
| lead                   | 中央寄せ                       |
| side-5-5               | 左右に1:1で分割                |
| side-3-7               | 左右に3:7で分割                |
| side-2-8               | 左右に1:4で分割                |
| side-no-title          | 左右分割でタイトルなし         |
| blockquote-side-2-8    | 上に引用、下が左右1:4で分割    |
| full                   | 四隅のパディングやマージンなし |
| narration-white        | 白文字のナレーションを中央に   |
| text-dimmed-background | 暗転背景にテキスト             |

---

<!-- _class: lead -->

## 画面中央で

### 語るスライド

---

<!-- _class: full -->

## 周囲のパディングやマージンなし

- hogehoge
  - hogehoge

---

## 画像のセンタリング

![neovim-girl center w:960](https://publish-01.obsidian.md/access/35d05cd1bf5cc500e11cc8ba57daaf88/Notes/attachments/neovim-girl-1280.webp)

---

## 画像のドロップシャドー

![neovim-girl drop-shadow center w:960](https://publish-01.obsidian.md/access/35d05cd1bf5cc500e11cc8ba57daaf88/Notes/attachments/neovim-girl-1280.webp)

---

<!-- 画像一枚 -->
<!-- _class: full lead -->

![bg neovim-girl](https://publish-01.obsidian.md/access/35d05cd1bf5cc500e11cc8ba57daaf88/Notes/attachments/neovim-girl-1280.webp)

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

<!-- _class: lead -->
<!-- 画面中央で引用を紹介 -->

> もともと私はアンチVimだった。なぜなら、AutoHotkeyを使ってOSレベルで効率的なキーバインドを実現していたからだ。その全容は🦉Spinal reflex bindings templateというリポジトリで管理している。
> 
> 🦉Spinal reflex bindings templateの設計思想はVimのモードに近しいものがある。だからこそ、それに満足しており、苦労してまでVimを覚える気にはなれなかったのだ。
> 
> ところが、このときの私は大きな誤解をしていた。**_私が分かったつもりでいたVimの思想は氷山の一角に過ぎなかったのである_**。
> 
> それに気付かせてくれた名著こそが📚実践Vimだ。📚実践Vimを読んで、私ははじめてVimの思想が何たるかを理解することができた。
> [📗Vimの思想を取り入れる \- Minerva](https://minerva.mamansoft.net/%F0%9F%93%97Productivity%E3%82%92%E4%B8%8A%E3%81%92%E3%82%8B%E3%81%9F%E3%82%81%E3%81%AB%E5%A4%A7%E5%88%87%E3%81%AA100%E3%81%AE%E3%81%93%E3%81%A8/%F0%9F%93%97Vim%E3%81%AE%E6%80%9D%E6%83%B3%E3%82%92%E5%8F%96%E3%82%8A%E5%85%A5%E3%82%8C%E3%82%8B)

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

---
