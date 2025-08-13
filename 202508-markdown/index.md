---
theme: mamansoft
_class: lead
paginate: true
---

<script src="https://cdn.tailwindcss.com/3.4.16"></script>
<script>tailwind.config = { corePlugins: { preflight: false } }</script>

<!-- _class: full lead text-dimmed-background slide-title -->

<div class="z-50 pt-48">
  <div class="title pb-64">
    Markdown Documentationのススメ
  </div>
  <div class="flex flex-col items-end">
    <div class="name">Tadashi Aikawa</div>
    <div class="date-and-event">2025/08/13 Minerva Lightning Talks</div>
  </div>
</div>

![bg](./attachments/minerva.avif)

<div class="absolute bg-black/75 w-full h-full"></div>

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
      <span>Mac / Windows(AI)</span>
    </div>
    <div class="item">
      <div class="label">ターミナル</div>
      <span>Ghostty</span>
    </div>
    <div class="item">
      <div class="label">言語</div>
      <span>TypeScript >> Python = Go > Lua > Rust</span>
    </div>
    <div class="item">
      <div class="label">エディタ</div>
      <span>Neovim / <em>Obsidian</em> </span>
    </div>
    <div class="item">
      <div class="label">デバイス</div>
      <span>EIZO / HHKB Studio</span>
    </div>
    <div class="item">
      <div class="label">サイト</div>
      <a href="https://minerva.mamansoft.net/"><em>Minerva</em></a>
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

## ドキュメンテーション経歴


| 年(大体)   | ツール             | 言語              | ホスティング      |
| ---------- | ------------------ | ----------------- | ----------------- |
| 2010～2012 | PukiWiki           | wiki              | 〃                |
| 2012～2013 | Google Site        | 独自              | 〃                |
| 2013～2015 | Sphinx             | reStructuredText  | Read the Docs     |
| 2013～2017 | Wordpress (ブログ) | 独自              | 自前サーバー      |
| 2015～2019 | _Markdown_         | _Markdown_        | Dropbox           |
| 2017～2021 | Hugo (ブログ)      | _Markdown_        | Netlify -> Vercel |
| 2019～2021 | _MkDocs_           | _Markdown_        | Netlify -> Vercel |
| 2021〜2025 | _Obsidian_         | _Markdown_ + wiki | Obsidian Publish  |


<div class="tag-note">会社では最近までobsidian.nvimを使っていました</div>

---

## Obsidianと私

![bg right:30%](https://publish-01.obsidian.md/access/35d05cd1bf5cc500e11cc8ba57daaf88/Notes/attachments/minerva-standup.webp)

- Obsidian歴 4年半
  - v0.10からDiscordに参加
- プラグイン開発者
  - [Various Complements] `35万DL` `★746`
  - [Another Quick Switcher] `10万DL` `★327`
- [Minerva]の管理人
  - [Obsidian Publish]で管理しているPKMサイト
  - 総ファイル数 10000以上
- [Obsidian Advent Calendar 2023]の発起人
  - Obsidianのアドベントカレンダーはおそらく日本で初

[Various Complements]: https://github.com/tadashi-aikawa/obsidian-various-complements-plugin
[Another Quick Switcher]: https://github.com/tadashi-aikawa/obsidian-another-quick-switcher
[Minerva]: https://minerva.mamansoft.net/
[Obsidian Publish]: https://help.obsidian.md/Obsidian+Publish/Introduction+to+Obsidian+Publish
[Obsidian Advent Calendar 2023]: https://adventar.org/calendars/8783

---

<!-- _class: chapter-divider -->

<div class="left">

### Agenda

</div>

<div class="right">

1. なぜMarkdownでドキュメントを管理するのか？
2. Markdownドキュメントを楽に管理するには？
3. Markdownドキュメントを共有するには？
4. まとめ

</div>

---

<!-- _class: chapter-divider -->

<div class="left">

### Chapter

## 01

</div>

<div class="right">

1. **なぜMarkdownでドキュメントを管理するのか？**
2. Markdownドキュメントを楽に管理するには？
3. Markdownドキュメントを共有するには？
4. まとめ

</div>

---

## 3つの理由

1. 個人のメモ/タスク管理に向いている
2. プロダクトドキュメントの管理に向いている
3. AIとの相性が良い

---

## 1. 個人のメモ/タスク管理に向いている

- ローカル管理でサクサク
- 情報の関連付けに強い
- 検索・加工しやすい (個人差あり)

---

## 2. プロダクトドキュメントの管理に向いている

- 情報の関連付けに強い
- Gitでバージョン管理できる
  - 変更履歴を追いやすい
  - ドキュメントもブランチで編集できる
  - PRレビューできる

---

## 3. AIとの相性が良い

- ローカルファイルなので読み込みが速く、入力情報量も多い
  - SaaS MCPだと検索APIの性能がボトルネックになりがち
- テキストなのでAIとコミュニケーションしやすい
  - Jiraのようなことは大体できる
- プロダクトコードの仕様と実装をセットで共有できる
  - プロンプトで仕様や経緯の説明をしなくても話が進む

---

## ただMarkdownにはこんな意見も... 

- NotionやConfluenceなどと比べて見にくい
- 整合性を担保しながら編集するのが辛い
  - リンク先に変更・削除があったときの対応など

```
### 3. Grep

This feature requires [ripgrep](https://github.com/BurntSushi/ripgrep) and set the executable command to "Ripgrep command" option.

![Demo](https://raw.githubusercontent.com/tadashi-aikawa/obsidian-another-quick-switcher/master/demo/grep.gif)

It sorts results by modified time descending.

#### Additional hotkeys


| Command | Description | Default Hotkey |
|---------|-------------|----------------|
| Search | Execute search | `TAB` |
| Preview | Preview selected file | `Ctrl+,` |
| Toggle input focus | Switch focus between search query and path input | _(customizable)_ |
| Clear input | Clear the search query input | _(customizable)_ |
| Clear path | Clear the path input | _(customizable)_ |
| Set ./ to path | Set current directory to path input | _(customizable)_ |
```

---

<!-- _class: chapter-divider -->

<div class="left">

### Chapter

## 02

</div>

<div class="right">

1. ~~なぜMarkdownでドキュメントを管理するのか？~~
2. **Markdownドキュメントを楽に管理するには？**
3. Markdownドキュメントを共有するには？
4. まとめ

</div>

---

<!-- _class: lead -->

## 適切なツールなしでドキュメントを書くのは
## IDEなしでコーディングするようなもの

---

## Markdownドキュメンテーションのためのツール構成例

<div class="grid-col-div-3 mt-12 text-primary" markdown="1">

  ![w:240](https://code.visualstudio.com/assets/images/code-stable.png)

  ![w:280](https://raw.githubusercontent.com/github/explore/26674e638508ac4a4e113ee32d6755ebfa000569/topics/neovim/neovim.png)

  ![w:240](https://cdn.svglogos.dev/logos/obsidian-icon.svg)

</div>

<div class="grid-col-div-3 pt-4">

<div class="text-3xl font-bold">
VSCode + <a href="https://github.com/foambubble/foam">Foam</a>
</div>

<div class="text-3xl font-bold">
Neovim + <a href="https://github.com/epwalsh/obsidian.nvim" class="text-[80%]">obsidian.nvim</a>
</div>

<div class="text-3xl font-bold">
<em>Obsidian</em>
</div>

</div>

---

## Obsidianとは `ローカルでMarkdownの知識ベース(PKM)を管理するアプリケーション`

<div class="drop-shadow">

![center h:540](https://obsidian.md/images/screenshot-1.0-hero-combo.png)

</div>

<footer>

[Obsidian - Sharpen your thinking](https://obsidian.md/) より引用

</footer>

---

## Obsidianのオススメポイント

- 圧倒的な速さ
  - 12065ファイルで起動速度0.5秒くらい
  - プラグインを入れると遅くなるケースあり
- 見た目の美しさ
  - [Live Preview]
  - [Stack tab groups]
- カスタマイズ性の高さ
  - 2500以上のプラグイン
  - TypeScript/JavaScriptで自由自在
  - CSSで自分好みの見た目に

[Live Preview]: https://help.obsidian.md/Live+preview+update
[Stack tab groups]: https://help.obsidian.md/tabs#Stack+tab+groups

---

## IDEのように快適な操作


| 操作                       | 利用するプラグイン       | 備考       |
| -------------------------- | ------------------------ | ---------- |
| 定義ジャンプ               | なし(標準)               |            |
| リネーム                   | なし(標準)               |            |
| リンクのオートコンプリート | [Various Complements]    | 標準でも可 |
| ファイル検索               | [Another Quick Switcher] | 標準でも可 |
| 呼出履歴                   | [Another Quick Switcher] | 標準でも可 |
| Git操作                    | [Obsidian Git]           |            |
| Vimモード                  | なし(標準)               |            |


[Obsidian Git]: https://github.com/denolehov/obsidian-git

---

## Wikiリンクのメリット

- 文字数が少ない
  - Markdownリンク: `[Obsidian](./Obsidian.md)`
  - Wikiリンク: `[[Obsidian]]`
- 場所に依存しない
  - Markdownリンク: `[Markdown](./glossaries/languages/Markdown.md)`
  - Wikiリンク: `[[Markdown]]`
- 自然に文章が書ける/読める
  - Markdownリンク: `[Obsidian](./Obsidian.md)は[Markdown](./languages/Markdown.md)が書きやすい`
  - Wikiリンク: `[[Obsidian]]は[[Markdown]]が書きやすい`

---

<!-- _class: chapter-divider -->

<div class="left">

### Chapter

## 03

</div>

<div class="right">

1. ~~なぜMarkdownでドキュメントを管理するのか？~~
2. ~~Markdownドキュメントを楽に管理するには？~~
3. **Markdownドキュメントを共有するには？**
4. まとめ

</div>

---

<!-- _class: lead -->

# MkDocsを使おう

---

## Mkdocsとは `Python製のSSG。Markdownベースのドキュメントをデプロイできる。`

<div class="drop-shadow">

<iframe src="https://www.mkdocs.org/" width="100%" height="540" frameborder="0" allowfullscreen class="mt-6"></iframe>

</div>

<footer>

[MkDocs](https://www.mkdocs.org/)

</footer>

---

## Material for MkDocs

<div class="drop-shadow">

<iframe src="https://squidfunk.github.io/mkdocs-material/" width="100%" height="540" frameborder="0" allowfullscreen class="mt-6"></iframe>

</div>

<footer>

[MkDocs](https://www.mkdocs.org/)

</footer>

---

## Obsidianとの互換性を保つ

<div class="drop-shadow">

<iframe src="https://minerva.mamansoft.net/2025-02-23-mkdocs-obsidian-compatible-docs" width="117%" height="660" frameborder="0" allowfullscreen class="mt-6 iframe-zoom-out"></iframe>

</div>

<footer>

[📘MkDocsでObsidianと互換性の高いドキュメントベースを実現する - Minerva](https://minerva.mamansoft.net/2025-02-23-mkdocs-obsidian-compatible-docs)

</footer>

---

## 利用例

<iframe src="https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/" width="117%" height="660" frameborder="0" allowfullscreen class="mt-6 iframe-zoom-out"></iframe>

<footer>

[Home - Various Complements](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/)

</footer>

---

<!-- _class: chapter-divider -->

<div class="left">

### Chapter

## 04

</div>

<div class="right">

1. ~~なぜMarkdownでドキュメントを管理するのか？~~
2. ~~Markdownドキュメントを楽に管理するには？~~
3. ~~Markdownドキュメントを共有するには？~~
4. **まとめ**

</div>

---

## まとめ

**Markdownドキュメントは**

- 『PKM』や『個人タスク管理』、『プロダクトドキュメント』と相性がいい
- Obsidianを使いこなすと快適に管理できる
- MkDocsでデプロイすると、他の人と共有できる

---

<!-- _class: lead -->

# おまけ

---

## ドキュメントを書き始める前に考えるべきことは？

ノートの作成場所をできるだけ _単一ディレクトリ_ 配下にしたほうがいい。

- 同名ノート( = 同名用語)の存在に気づける
- ドキュメンテーションビルダーでトラブルが発生しにくい
- エディタでトラブルが発生しにくい

---

## Markdownドキュメンテーションが向かないものは？

以下の条件を満たすようなものはやめたほうがいいかも。

- 色々なPJから*予期せず*参照されることが多い
- Markdownを書けない人が編集する機会が多い
- プロダクトと関連性が弱い (PJ定例など)
- リアルタイムで『編集 *&* 共有』が必要

---

## オススメのObsidianプラグイン (主観)


| プラグイン名               | 用途                               |
| -------------------------- | ---------------------------------- |
| 🦉 [Various Complements]    | オートコンプリート                 |
| 🦉 [Another Quick Switcher] | Vault内のファイル確認・移動        |
| [Vimrc Support Plugin]     | vimrcサポート                      |
| [Periodic Notes]           | Daily Note / Weekly Report         |
| 🦉 [Silhouette]             | タスク管理 (非公式)                |
| 🦉 [Carnelian]              | army knife (非公式) (今は自分専用) |


[Vimrc Support Plugin]: https://github.com/esm7/obsidian-vimrc-support
[Periodic Notes]: https://github.com/liamcain/obsidian-periodic-notes/
[Silhouette]: https://github.com/tadashi-aikawa/silhouette
[Carnelian]: https://github.com/tadashi-aikawa/carnelian

---

## 世間で人気そうなObsidianプラグイン


| プラグイン名     | 用途                               |
| ---------------- | ---------------------------------- |
| [Omni Search]    | Vault内検索                        |
| [Obsidian Tasks] | タスク管理                         |
| [Kanban]         | カンバン                           |
| [Templater]      | JavaScriptで即席処理               |
| [Dataview]       | Confluenceのデータベース機能っぽい |


[Omni Search]: https://github.com/scambier/obsidian-omnisearch
[Obsidian Tasks]: https://github.com/obsidian-tasks-group/obsidian-tasks
[Kanban]: https://github.com/mgmeyers/obsidian-kanban
[Templater]: https://github.com/SilentVoid13/Templater
[Dataview]: https://github.com/blacksmithgu/obsidian-dataview

<div class="note">
※ Templaterについて<br/>
Obsidian 1.9でBasesという同様のコアプラグインが追加されるので待ったほうがいいかも
</div>

