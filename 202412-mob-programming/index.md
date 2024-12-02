---
theme: mamansoft
_class: lead
paginate: true
---

<script src="https://cdn.tailwindcss.com/3.4.4"></script>
<script>tailwind.config = { corePlugins: { preflight: false } }</script>

<!-- _class: slide-title -->

<div class="title">
  <div>モブプロを取り入れるとき</div>
  <div>必要のないとき</div>
</div>
<div class="name">Tadashi Aikawa</div>
<div class="date-and-event">2024/12/01 Minerva Lightning Talks</div>

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
      <div class="label">言語</div>
      <span>TypeScript >> Python = Go = Rust > Lua</span>
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

1. モブプロとは
2. 手段としてのモブプロ
3. モブプロのロール
4. まとめ

</div>

---

<!-- _class: chapter-divider -->

<div class="left">

### Chapter

## 01

</div>

<div class="right">

1. **モブプロとは**
2. 手段としてのモブプロ
3. モブプロのロール
4. まとめ

</div>

---

## モブプロとは

- 正式名称『モブプログラミング』
- 皆で集まり、『同じ時間』『同じ場所』で『同じモノ』を開発する手法
- 一般的に参加者は3名以上だが、**本スライドでは2名の場合も含める**

---

## モブプロは時間の無駄ではないか..??

- みんなで集まって、しかも1つのタスクしか進行できない
- 自席よりもあらゆる環境が劣っており生産性が悪い
  - 『モニタが1台? 冗談だろ??』
  - 『椅子が悪いから腰が痛いよ..』
  - 『結局みんな非効率な環境で内職してるだけさ hahaha』
- 新人は操作が遅いし、熟練者がすべて伝えるだけ時間の無駄
- 熟練者が操作すると、新人はついていけなくて置いてかれるだけ
- 『今週予定のタスクが進捗よくないので欠席で』
- 『1人で苦労しなければいつまでも半人前よ』

---

<!-- _class: lead -->

# 半分正解
# だけど半分不正解

## タスクとチームの状況によって変わってくる

---

<!-- _class: chapter-divider -->

<div class="left">

### Chapter

## 02

</div>

<div class="right">

1. ~~モブプロとは~~
2. **手段としてのモブプロ**
3. モブプロのロール
4. まとめ

</div>

---

<!-- _class: lead -->

# そもそもモブプロは *手段*

---

## リソース効率とフロー効率

<div class="mt-24">

![center w:540](https://image.slidesharecdn.com/xp2017-170916011815/75/xpjug-1-2048.jpg)

</div>

<footer>

[フロー効率性とリソース効率性について \#xpjug \| PPT XP祭り2017の公開スライドより](https://www.slideshare.net/slideshow/xpjug/79824686)

</footer>

---

## リソース効率重視であることが垣間見えるワード

- 『**〇〇さん** にタスクをふらなきゃ』
- 『**〇〇さん** が「やることがない」と言っていました』
- 『**〇〇さん** の予定と実績はどうなってる?』

---

## リソース効率重視であることが垣間見えるワード

- 『**〇〇さん** にタスクをふらなきゃ』
- 『**〇〇さん** が「やることがない」と言っていました』
- 『**〇〇さん** の予定と実績はどうなってる?』

<div class="center h-half">

### **人** が主語や目的語になる会話が増える

</div>

---

## フロー効率重視であることが垣間見えるワード

- 『来週までに〇〇できるようにしよう』
- 『どうすれば〇〇できるだろうか?』
- 『〇〇の優先度は今はどうなってる?』

---

## フロー効率重視であることが垣間見えるワード

- 『来週までに〇〇できるようにしよう』
- 『どうすれば〇〇できるだろうか?』
- 『〇〇の優先度は今はどうなってる?』

<div class="center h-half">

### **タスク** が主語や目的語になる会話が増える

</div>

---

<!-- _class: lead -->

# どちらが 良い/悪い ではない
### タスク・チーム状況によって
### どちらの効率をどれだけ重視するべきかは変わる

---

## タスクによってどちらを重視すべきかの指標例

|                            | *リソース効率*重視 | *フロー効率*重視 |
|----------------------------|--------------------|------------------|
| **不確実性**               | 低い               | 高い             |
| **レビュー差し戻しリスク** | 低い               | 高い             |
| **影響範囲**               | 狭い               | 広い             |
| **チームメンバの作業待ち** | ほぼ無い           | ある             |


---

<!-- _class: lead -->

# そもそもモブプロは *手段*

<div class="tag-note">
再掲
</div>

---

<!-- _class: lead -->

## リソース効率重視のタスクなら

## そもそも*不要*

---

<!-- _class: lead -->

## では、フロー効率重視のタスクなら

## *必ず*モブプロをやった方がいいのか?

---

<!-- _class: lead -->

# どちらが 良い/悪い ではない
### タスク・チーム状況によって
### どちらの効率をどれだけ重視するべきかは変わる

<div class="tag-note">
再掲
</div>

---

<!-- _class: lead -->

# どちらが 良い/悪い ではない
### タスク・*チーム状況*によって
### どちらの効率をどれだけ重視するべきかは変わる

<div class="tag-note">
再掲
</div>

---

## これらができるチームなら やり方はなんでもいい

- 個人に十分な業務遂行能力がある
  - 1人で案件の要件定義からリリースまでできる
  - 必要に応じて相談ができる
- プロジェクトの状況を見極め *自発的に考えて* 次のアクションをとれる 
  - 指示待ちになったり、暇になることはない
- 状況に応じて必要な知識をチームメンバ全員で共有できている
  - Slack、口頭コミュニケーションなどを利用
  - 日常的に *発信*と**受信** できていることが大事

---

<!-- _class: lead -->

# かなり高いハードルだと思います...

---

<!-- _class: lead -->

# そんな貴方に『モブプロ』

---

<!-- _class: chapter-divider -->

<div class="left">

### Chapter

## 03

</div>

<div class="right">

1. ~~モブプロとは~~
2. ~~手段としてのモブプロ~~
3. **モブプロのロール**
4. まとめ

</div>

---

<!-- _class: lead -->

# 集団戦で大事なこと...

## それは役割(ロール)を意識することだ

---

<!-- _class: lead -->

> MOB PROGRAMMING: THE ROLE PLAYING GAME
> by Willem Larsen CC-BY-SA-NC 2016
> Powered by the Apocalypse - thanks to BigBadCon 2016 for inspiration
[willemlarsen/mobprogrammingrpg](https://github.com/willemlarsen/mobprogrammingrpg)

---

<!-- _class: grid-cross -->

## モブプロのロール (一部のみ)

<div class="leftup">

### LV1

- *タイピスト* `Driver`
- *ナビゲーター* `Navigator`
- モブ `Mobber`

</div>

<div class="rightup">

### LV2

- *研究者* `Researcher`
- 後援者 `Sponsor`
- 提督 `Rear Admiral`

</div>

<div class="leftdown">

### LV3

- 自動化担当 `Automationist`
- *司書* `Archivist`
- 鼻担当 `Nose`

</div>

<div class="rightdown">

### LV4

- 交通警察 `Traffic Cop`
- 痛み担当 `Major Pain`

</div>

---

<!-- _class: lead -->

## 各ロールの定義はリポジトリ参照

### `jp`ディレクトリ配下に日本語もあります

---

## 4人でやる場合にオススメなロールパーティー

- **タイピスト** `Driver` (必須)
- **ナビゲーター** `Navigator` (必須)
- 研究者 `Researcher`
- 司書 `Archivist`

<small>※ モブの最中はずっと同じロールである必要はなく、むしろローテーションを推奨</small>

---

## 6人でやる場合にオススメなロールパーティー

- **タイピスト** `Driver` (必須)
- **ナビゲーター** `Navigator` (必須)
- 研究者 `Researcher`
- 提督 `Rear Admiral`
- 司書 `Archivist`
- 自動化担当 `Automationist`

<small>※ モブの最中はずっと同じロールである必要はなく、むしろローテーションを推奨</small>

---

<!-- _class: chapter-divider -->

<div class="left">

### Chapter

## 04

</div>

<div class="right">

1. ~~モブプロとは~~
2. ~~手段としてのモブプロ~~
3. ~~モブプロのロール~~
4. **まとめ**

</div>

---

## まとめ

- モブプロは*フロー効率重視の作業を矯正する手段*
- モブプロをすべきかどうかは*タスク*と*チーム状況*による
- モブプロ実施の際は*ロール*を意識するとよい

---

<!-- _class: lead -->

# おまけ

---

## 個人的にチーム開発で大切にしていること

- **始めること**よりも*終わらせること*を大事にしよう
  - リリースできる状態にしてはじめて**終わらせた**と言える
  - 実装が終わっただけでは最悪の場合は未着手と同じ
- **1人で**やりきるのではなく*チームで最速の方法*を考えよう
  - 3人で1時間30分で終わるなら、1時間30分後にリリースができる
  - 1人で4時間頑張って、レビューを数往復して2日後になったら..??
- **モブプロが必要なのに時間を作れない**なら*タスクの優先度*を考えなおそう
  - *すべてが最優先*だと、モブは成立せず個人のタスクを優先してしまう
  - ただし *兼務をしている場合* は除く

