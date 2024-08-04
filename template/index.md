---
theme: mamansoft
_class: lead
paginate: true
backgroundColor: #fff
backgroundImage: url('https://marp.app/assets/hero-background.svg')
---

<script src="https://cdn.tailwindcss.com/3.4.4"></script>
<script>tailwind.config = { corePlugins: { preflight: false } }</script>

# テンプレート

### yyyy-mm-dd title

#### tadashi-aikawa

---

<!-- _class: full side-3-7 side-no-title -->

<div class="flex justify-center items-center">
  <img src="https://publish-01.obsidian.md/access/35d05cd1bf5cc500e11cc8ba57daaf88/Notes/attachments/Pasted%20image%2020210605212644.png" height="100%" />
</div>

<div class="py-12">
  <h1>Tadashi Aikawa</h1>
  <h5 class="text-secondary">Productivity Creator since 2010</h5>
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
      <code class="w-48 text-center">キーボード</code>
      <span class="pl-2">HHKB Studio</span>
    </div>
    <div>
      <code class="w-48 text-center">サイト/ブログ</code>
      <a class="pl-2" href="https://minerva.mamansoft.net/">Minerva</a>
    </div>
    <div>
      <code class="w-48 text-center">GitHub</code>
      <a class="pl-2" href="https://github.com/tadashi-aikawa">tadashi-aikawa</a>
    </div>
    <div>
      <code class="w-48 text-center">SNS</code>
      <a class="pl-2" href="https://bsky.app/profile/tadashi-aikawa.bsky.social">
        @tadashi-aikawa.bsky.social
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

## 利用できるclass

| クラス名            | 用途                        |
|---------------------|-----------------------------|
| side-5-5            | 左右に1:1で分割             |
| side-3-7            | 左右に3:7で分割             |
| side-2-8            | 左右に1:4で分割             |
| blockquote-side-2-8 | 上に引用、下が左右1:4で分割 |

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
