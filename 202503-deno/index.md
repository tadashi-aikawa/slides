---
theme: mamansoft
_class: lead
paginate: true
---

<script src="https://cdn.tailwindcss.com/3.4.16"></script>
<script>tailwind.config = { corePlugins: { preflight: false } }</script>

<!-- _class: slide-title relateive -->

<div class="title">
  <div>Denoはイイゾ</div>
  <div class="pt-16"><i class="nf nf-dev-denojs text-[3em]"></i></div>
</div>
<div class="name">Tadashi Aikawa</div>
<div class="date-and-event">2025/03/02 Minerva Lightning Talks</div>

---

![bg left:30%](https://publish-01.obsidian.md/access/35d05cd1bf5cc500e11cc8ba57daaf88/Notes/attachments/Pasted%20image%2020210605212644.png)

<style scoped>
.item {
  display: flex;
  align-items: center;
  gap: 0.75em;
}
</style>

<div>
  <h1 class="text-foreground">Tadashi Aikawa</h1>
  <h5 class="text-dimmed">Productivity Creator since 2010</h5>
  <div class="mt-12 space-y-2 text-2xl">
    <div class="item">
      <div class="label">OS</div>
      <span>Windows <small>(開発はUbuntu on WSL)</small></span>
    </div>
    <div class="item">
      <div class="label">ターミナル</div>
      <span>Windows Terminal / WezTerm (secondary)</span>
    </div>
    <div class="item">
      <div class="label">言語</div>
      <span>TypeScript >> Python = Go > Lua > Rust</span>
    </div>
    <div class="item">
      <div class="label">エディタ</div>
      <span>Neovim / Obsidian</span>
    </div>
    <div class="item">
      <div class="label">デバイス</div>
      <span>EIZO / HHKB Studio / SlimBlade</span>
    </div>
    <div class="item">
      <div class="label">サイト</div>
      <a href="https://minerva.mamansoft.net/">Minerva</a>
      <a href="https://github.com/tadashi-aikawa">GitHub</a>
      <a href="https://bsky.app/profile/tadashi-aikawa.bsky.social">
        Bluesky
      </a>
    </div>
    <div class="item">
      <div class="label">好き</div>
      <span>創作活動・温泉・甘味・動物(ぬいぐるみ含む)</span>
    </div>
    <div class="item">
      <div class="label">苦手</div>
      <span>お酒・車・勉強</span>
    </div>
    <div class="item">
      <div class="label">楽しい仕事</div>
      <span>個人やチームの生産性を上げて成果に繋げる</span>
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

1. What is Deno?
2. Deno vs Node.js
3. Why Deno?
4. How I Use Deno

</div>

---

<!-- _class: chapter-divider -->

<div class="left">

### Chapter

## 01

</div>

<div class="right">

1. **What is Deno?**
2. Deno vs Node.js
3. Why Deno?
4. How I Use Deno

</div>

---

## Denoとは `モダンWebのためのJavaScriptランタイム`

<div class="drop-shadow">

![center h:540](./resources/2025-03-02_13h08_42.png)

</div>

<footer>

[Deno, the next\-generation JavaScript runtime](https://deno.com/)

</footer>

---

## Denoの主な特徴

- **TypeScript / JavaScript のランタイム**
- **開発/デプロイに必要なツールが同梱済**
- **Node.jsとの互換レイヤーあり**
- モダンWeb対応 / Web標準API優先
- deny -> allow な堅牢セキュリティー設計
- v8エンジン使用
- Rust製

<div class="note">※ 太字の項目は後ほど説明</div>

<footer>

[Deno, the next\-generation JavaScript runtime](https://deno.com/)

</footer>

---

<!-- _class: chapter-divider -->

<div class="left">

### Chapter

## 02

</div>

<div class="right">

1. ~~What is Deno?~~
2. **Deno vs Node.js**
3. Why Deno?
4. How I Use Deno

</div>

---

## Deno と Node.js `※ 2025/03/02 時点の情報、標準搭載機能のみ`

|                  | Node.js   | Deno v1    | Deno v2   |
| -                | -         | -          | -         |
| 作者             | Ryan Dahl | Ryan Dahl  | Ryan Dahl |
| 安定版公開       | 2015年    | 2020年     | 2024年    |
| GitHubスター数   | 110k      | 102K       | 102K      |
| TypeScript       | 未対応    | *対応*     | *対応*    |
| パッケージ管理   | npm       | URL        | URL, npm  |
| CommonJS         | 対応      | ほぼ未対応 | 部分対応  |
| ESM              | 対応      | 対応       | 対応      |
| シングルバイナリ | 未対応    | *対応*     | *対応*    |

---

## Deno v1 は Node.js と互換性がほぼ無かった

|                  | *Node.js* | *Deno v1*    | Deno v2   |
| -                | -         | -            | -         |
| 作者             | Ryan Dahl | Ryan Dahl    | Ryan Dahl |
| 安定版公開       | 2015年    | 2020年       | 2024年    |
| GitHubスター数   | 110k      | 102K         | 102K      |
| TypeScript       | 未対応    | 対応         | 対応      |
| パッケージ管理   | *npm*     | *URL*        | URL, npm  |
| CommonJS         | *対応*    | *ほぼ未対応* | 部分対応  |
| ESM              | 対応      | 対応         | 対応      |
| シングルバイナリ | 未対応    | 対応         | 対応      |

---

## Deno v2 では Node.js に歩み寄った形に

|                  | *Node.js* | Deno v1    | *Deno v2*  |
| -                | -         | -          | -          |
| 作者             | Ryan Dahl | Ryan Dahl  | Ryan Dahl  |
| 安定版公開       | 2015年    | 2020年     | 2024年     |
| GitHubスター数   | 110k      | 102K       | 102K       |
| TypeScript       | 未対応    | 対応       | 対応       |
| パッケージ管理   | *npm*     | URL        | URL, *npm* |
| CommonJS         | *対応*    | ほぼ未対応 | *部分対応* |
| ESM              | 対応      | 対応       | 対応       |
| シングルバイナリ | 未対応    | 対応       | 対応       |

---

<!-- _class: chapter-divider -->

<div class="left">

### Chapter

## 03

</div>

<div class="right">

1. ~~What is Deno?~~
2. ~~Deno vs Node.js~~
3. **Why Deno?**
4. How I Use Deno

</div>

---

## なぜDenoか？

1. TypeScriptが `deno run *.ts` でいきなり動く
2. Linter/Formatter/Test がバンドル済で設定不要
3. シングルバイナリへビルド可能 (Windows/macOS/Linux)

---

<div class="center">
  <video muted controls src="./resources/2025-03-02-14-44-37.webm" height="620"></video>
</div>

---

<!-- _class: chapter-divider -->

<div class="left">

### Chapter

## 04

</div>

<div class="right">

1. ~~What is Deno?~~
2. ~~Deno vs Node.js~~
3. ~~Why Deno?~~
4. **How I Use Deno**

</div>

---

## 私がDenoをつかうとき `Web開発以外ならチャンスあり`

| 用途                   | 備考                                | 作成プロダクト    |
| -                      | -                                   | -                 |
| **学習**               | TypeScriptバージョン指定がない場合  | [TDQ]             |
| **使い捨てスクリプト** |                                     |                   |
| **CLIツール**          | [Cliffy]を使う                      |                   |
| **API**                | 小規模の場合 (それ以上は[Hono]など) |                   |
| **ライブラリ**         | [JSR]にアップロードする場合         | [Silhouette Core] |
| **Neovimプラグイン**   | [Denops]を利用する                  | [Silhouette.nvim] |

[Cliffy]: https://cliffy.io/
[JSR]: https://jsr.io/
[Denops]: https://github.com/vim-denops/denops.vim
[Hono]: https://hono.dev/
[TDQ]: https://minerva.mamansoft.net/%F0%9F%93%97TDQ/%F0%9F%93%92TDQ
[Silhouette Core]: https://jsr.io/@tadashi-aikawa/silhouette-core
[Silhouette.nvim]: https://github.com/tadashi-aikawa/silhouette.nvim

---

## まとめ `Denoはイイゾ`

- 数秒でTypeScriptの開発がスタートできる 
- 小さなプロダクトや使い捨てコードには積極的に使おう
- 依存ライブラリが多いプロダクトや、既存プロダクトへの導入は検討が必要

---

## 付録 `TDQより`

| タイトル                           | 内容                 |
| -                                  | -                    |
| [TDQ-001 JavaScriptの実行環境構築] | インストール, REPL   |
| [TDQ-002 JavaScriptの開発環境構築] | VSCodeの環境構築     |
| [TDQ-010 Denoのテスト]             | テストコードの書き方 |

[TDQ-001 JavaScriptの実行環境構築]: https://minerva.mamansoft.net/%F0%9F%93%97TDQ/%F0%9F%93%97TDQ-001+JavaScript%E3%81%AE%E5%AE%9F%E8%A1%8C%E7%92%B0%E5%A2%83%E6%A7%8B%E7%AF%89
[TDQ-002 JavaScriptの開発環境構築]: https://minerva.mamansoft.net/%F0%9F%93%97TDQ/%F0%9F%93%97TDQ-002+JavaScript%E3%81%AE%E9%96%8B%E7%99%BA%E7%92%B0%E5%A2%83%E6%A7%8B%E7%AF%89
[TDQ-010 Denoのテスト]: https://minerva.mamansoft.net/%F0%9F%93%97TDQ/%F0%9F%93%97TDQ-010+Deno%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88

<div class="note">※ Neovimの環境構築はDeno以外との共存が少し大変なので別途聞いてください</div>

