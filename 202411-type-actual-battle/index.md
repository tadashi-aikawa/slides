---
theme: mamansoft
_class: lead
paginate: true
style: |
  pre code span {
    color: black;
  }
---

<script src="https://cdn.tailwindcss.com/3.4.4"></script>
<script>tailwind.config = { corePlugins: { preflight: false } }</script>

<!-- _class: slide-title -->

<div class="title">
  <div class="pb-8">
    <span class="mr-4">実戦</span>
    <span>型パズル</span>
  </div>
  <img src="./resources/language-typescript.svg" style="width: 4em; filter: var(--color-filter-white)" />
</div>
<div class="name">Tadashi Aikawa</div>
<div class="date-and-event">2024/11/17 Minerva Lightning Talks</div>

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

![bg left:30%](https://publish-01.obsidian.md/access/35d05cd1bf5cc500e11cc8ba57daaf88/Notes/attachments/Pasted%20image%2020210605212644.png)

<style scoped>
.item {
  display: flex;
  align-items: center;
  gap: 0.75em;
}
.item .label {
  font-size: 0.8em;
  font-weight: bold;
  height: 1.75em;
}
</style>

<div>
  <h3 class="text-foreground">Web系 年表</h3>
  <div class="mt-12 space-y-2 text-2xl">
    <div class="item">
      <div class="label">2010年</div>
      <span>エンジニアとして仕事をはじめる</span>
    </div>
    <div class="item">
      <div class="label">2012年</div>
      <span>はじめて<b>JavaScript</b>でモノをつくる</span>
    </div>
    <div class="item">
      <div class="label">2015年</div>
      <span>はじめて<b>React</b>でモノをつくる</span>
    </div>
    <div class="item">
      <div class="label" style="background-color: var(--color-primary);">2016年</div>
      <span>はじめて<b style="color: var(--color-primary)">TypeScript</b>でモノをつくる</span>
    </div>
    <div class="item">
      <div class="label">2017年</div>
      <span>はじめて<b>Angular2</b>でモノをつくる</span>
    </div>
    <div class="item">
      <div class="label" style="height: 3em; line-height: 3em;">2018年</div>
      <div>
        <div>はじめて<b>Vue2</b>でモノをつくる</div>
        <div>はじめて<b>VSCode拡張</b>をつくる</div>
      </div>
    </div>
    <div class="item">
      <div class="label">2019年</div>
      <span>はじめて<b>Chrome拡張</b>をつくる</span>
    </div>
    <div class="item">
      <div class="label" style="height: 3em; line-height: 3em;">2020年</div>
      <div>
        <div>はじめて<b>Vue3</b>でモノをつくる</div>
        <div>はじめて<b>Svelte</b>でモノをつくる</div>
      </div>
    </div>
    <div class="item">
      <div class="label">2021年</div>
      <span>はじめて<b>Obsidianプラグイン</b>をつくる</span>
    </div>
    <div class="item">
      <div class="label" style="height: 3em; line-height: 3em;">2023年</div>
      <div>
        <div>はじめて<b>Deno</b>でモノをつくる</div>
        <div>はじめて<b>Bun</b>でモノをつくる</div>
      </div>
    </div>
    <div class="item">
      <div class="label">2024年</div>
      <span>はじめて<b>Neovimプラグイン</b>をつくる</span>
    </div>
  </div>
</div>

---

<!-- _class: lead -->

## よくあるVueの選択要素実装(select)を通して

## 実戦で使えるTypeScriptの型スキルを学ぼう

<span class="tag-note">本日のお題</span>

---

<!-- _class: lead -->

## **25分のネタ**を*9分*で話します

### 分かっている人がなんとかついていけるレベルかなと

---

## ケーキを選択するvueファイル

<div class="grid-col-5-5" style="align-items: start">

<div>

```typescript
<script setup lang="ts">
import { computed, ref } from "vue";

const cakeList = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
];

const myCake = ref<any>("");

const message = computed(() => {
  switch (myCake.value.name) {
    case "ショートケーキ":
      return `上は ${myCake.value.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
  }
});
</script>
```

</div>

<div>

```html
<template>
  <select v-model="myCake">
    <option v-for="cake in cakeList" :value="cake">
      {{ cake.name }}
    </option>
  </select>
  <h1>{{ message }}</h1>
</template>
```

![drop-shadow w:560](./resources/demo.gif)

</div>

</div>

</div>

---

## TypeScriptコードの方に着目

```typescript
<script setup lang="ts">
import { computed, ref } from "vue";

const cakeList = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
];

const myCake = ref<any>("");

const message = computed(() => {
  switch (myCake.value.name) {
    case "ショートケーキ":
      return `上は ${myCake.value.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
  }
});
</script>
```

---

## さらにVueに関する部分を除外

```typescript
const cakeList = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
];

let myCake: any = "";

myCake = cakeList[0]; // 1番目の要素(=ショートケーキ)を選んだと仮定した処理

function getMessage() {
  switch (myCake.name) {
    case "ショートケーキ":
      return `上は ${myCake.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
  }
}
```

---

<!-- _class: lead -->

# 何が問題か?

---

## *変数myCakeをany型と宣言していること*が問題

```typescript
const cakeList = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
];

let myCake: any = ""; // myCakeをany型と宣言 (そもそもなぜ空文字?)
myCake = cakeList[0]; // 代入後もany ({ name: string, fruit: string }型って知ってるのに...)

function getMessage() {
  switch (myCake.name) { // myCake.nameもany
    case "ショートケーキ":
      return `上は ${myCake.fruit} だ！`; // myCake.fruitもany
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
  }
}
```

<footer>

[any型](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any)

</footer>

---

## 実際に起こる悲劇

```typescript
const cakeList = [ // 中身を変更してみる (『string[]でOk!』と勘違い...)
  "ショートケーキ",
  "チーズケーキ",
];

let myCake: any = "";
myCake = cakeList[0];

function getMessage() {
  switch (myCake.name) {
    case "ショートケーキ":
      return `上は ${myCake.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
  }
}
```

---

## 意図通り動かない。*エラーも出ない。*

```typescript
const cakeList = [
  "ショートケーキ",
  "チーズケーキ",
];

let myCake: any = "";
myCake = cakeList[0];

function getMessage() {
  switch (myCake.name) { // undefinedになる
    case "ショートケーキ":
      return `上は ${myCake.fruit} だ！`; // ここには永遠に来ない...
    case "チーズケーキ":
      return `チーズケーキおいしい!`; // ここには永遠に来ない...
  }
}
```

---

<!-- _class: lead -->

# どうすればいいの?

<div style="position: absolute; bottom: -10px; right: 0">

![w:320](./resources/typescript-faq.webp)

</div>

---

## *Cake型*を定義し、変数myCakeの型は*Cake型*だと宣言する

```typescript
const cakeList = [ "ショートケーキ", "チーズケーキ" ];

type Cake = { // Cake型の宣言
  name: string;   // 名前は必須
  fruit?: string; // フルーツが乗ってるかも?
}

let myCake: Cake = { name: "チーズケーキ" }; // any -> Cake に変更して、初期値も設定
myCake = cakeList[0];

function getMessage() {
  switch (myCake.name) {
    case "ショートケーキ":
      return `上は ${myCake.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
  }
}
```

---

## エラーが出るので実行前に気づける

```typescript
const cakeList = [ "ショートケーキ", "チーズケーキ" ];

type Cake = {
  name: string;
  fruit?: string;
}

let myCake: Cake = { name: "チーズケーキ" };
myCake = cakeList[0]; // ⛔ string型の値(ショートケーキ) は Cake型の変数(myCake) に入れられないのでエラー！

function getMessage() {
  switch (myCake.name) {
    case "ショートケーキ":
      return `上は ${myCake.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
  }
}
```

---

<!-- _class: lead -->

# ウォーミングアップ終了

---

## cakeListを元に戻して再開

```typescript
const cakeList = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
];

type Cake = {
  name: string;
  fruit?: string;
};

let myCake: Cake = { name: "チーズケーキ" };
myCake = cakeList[0];

function getMessage() {
  switch (myCake.name) {
    case "ショートケーキ":
      return `上は ${myCake.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
  }
}
```

---

## typoしちゃった...

```typescript
const cakeList = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
];

type Cake = {
  name: string;
  fruit?: string;
};

let myCake: Cake = { name: "チーズケーキ" };
myCake = cakeList[0];

function getMessage() {
  switch (myCake.name) {
    case "ショットケーキ": // typoしちゃった...
      return `上は ${myCake.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
  }
}
```

---

## typoしちゃった...けど*エラーは出ない*

```typescript
const cakeList = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
];

type Cake = {
  name: string;
  fruit?: string;
};

let myCake: Cake = { name: "チーズケーキ" };
myCake = cakeList[0];

function getMessage() {
  switch (myCake.name) {
    case "ショットケーキ":
      return `上は ${myCake.fruit} だ！`; // ⛔ ここには永遠に入らない
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
  }
}
```

---

## typoしちゃった...けど*エラーは出ない*

```typescript
const cakeList = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
];

type Cake = {
  name: string;
  fruit?: string;
};

let myCake: Cake = { name: "チーズケーキ" };
myCake = cakeList[0];

function getMessage() {
  switch (myCake.name) {
    case "ショットケーキ": // ここでエラーになってほしい (『ショットケーキなんてないぞ！』と)
      return `上は ${myCake.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
  }
}
```

---

## なぜエラーにしてくれないの?

```typescript
const cakeList = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
];

type Cake = {
  name: string;  // 1.Cake型のnameプロパティはstring型である
  fruit?: string;
};

let myCake: Cake = { name: "チーズケーキ" }; // 2.myCakeはCake型 (let宣言なので右辺の値は関係ない)
myCake = cakeList[0];

function getMessage() {
  switch (myCake.name) { // 3.Cake["name"]はstring型
    case "ショットケーキ": // 4.string型なら"ショットケーキ"の可能性もあるよね
      return `上は ${myCake.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
  }
}
```

---

<!-- _class: lead -->

# どうすればいいの?

<div style="position: absolute; bottom: -10px; right: 0">

![w:320](./resources/typescript-faq.webp)

</div>

---

## Cake["name"]を*文字列リテラルのユニオン型*にする

```typescript
const cakeList = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
];

type Cake = {
  name: "ショートケーキ" | "チーズケーキ"; // 1.文字列リテラルのユニオン型 に変更
  fruit?: string;
};

let myCake: Cake = { name: "チーズケーキ" };
myCake = cakeList[0];

function getMessage() {
  switch (myCake.name) { // 2.myCake.nameの値は "ショートケーキ" or "チーズケーキ"
    case "ショットケーキ": // ⛔ 3."ショットケーキ" はあり得ないのでエラー
      return `上は ${myCake.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
  }
}
```

<footer>

<div class="flex justify-center gap-8">

[リテラル型(Literal Types)](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#literal-types)

[ユニオン型(Union Types)](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#union-types)

</div>

</footer>

---

## それだけでは*myCakeの代入処理がエラー*になる

```typescript
const cakeList = [
  { name: "ショートケーキ", fruit: "イチゴ" }, // cakeList[0]["name"] の値はこれ -> cakeList[0].nameは可変なのでstring型と推論される)
  { name: "チーズケーキ" },
];

type Cake = {
  name: "ショートケーキ" | "チーズケーキ"; // myCake["name"] の型はこれ
  fruit?: string;
};

let myCake: Cake = { name: "チーズケーキ" };
myCake = cakeList[0]; // ⛔ cakeList[0]はmyCakeに代入できない (cakeList[0]["name"]の値はmyCake["name"]に代入できないから)

function getMessage() {
  switch (myCake.name) {
    case "ショットケーキ":
      return `上は ${myCake.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
  }
}
```

---

## cakeListも宣言時に型を指定してあげる

```typescript
const cakeList: Cake[] = [ // 1.Cake[]型 と宣言
  { name: "ショートケーキ", fruit: "イチゴ" }, // 2.cakeList[0] は Cake型 になる
  { name: "チーズケーキ" },
];

type Cake = {
  name: "ショートケーキ" | "チーズケーキ";
  fruit?: string;
};

let myCake: Cake = { name: "チーズケーキ" };
myCake = cakeList[0]; // 3.Cake型 に Cake型 の代入なので問題なし

function getMessage() {
  switch (myCake.name) {
    case "ショットケーキ": // ⛔ 4.ここもちゃんとエラーになる
      return `上は ${myCake.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
  }
}
```

---

<!-- _class: lead -->

# swtich文を深堀する

---

## 先ほどのコードからswitch文にフォーカスして抽出する

```typescript
const cakeList: Cake[] = [ 
  { name: "ショートケーキ", fruit: "イチゴ" }, 
  { name: "チーズケーキ" },
];

type Cake = {
  name: "ショートケーキ" | "チーズケーキ";
  fruit?: string;
};

let myCake: Cake = { name: "チーズケーキ" };
myCake = cakeList[0]; 

function getMessage() {
  switch (myCake.name) {
    case "ショットケーキ": 
      return `上は ${myCake.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
  }
}
```

---

## 先ほどのコードからswitch文に*フォーカスして抽出する*

```typescript
type Cake = {
  name: "ショートケーキ" | "チーズケーキ";
  fruit?: string;
};

declare const myCake: Cake;

function getMessage() {
  switch (myCake.name) {
    case "ショートケーキ":
      return `上は ${myCake.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
  }
}
```

---

## Cake["name"] が増えるとどうなる?

```typescript
type Cake = {
  name: "ショートケーキ" | "チーズケーキ" | "モンブラン"; // "モンブラン" を追加
  fruit?: string;
};

declare const myCake: Cake;

function getMessage() {
  switch (myCake.name) {
    case "ショートケーキ":
      return `上は ${myCake.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
  }
}
```

---

## モンブランの考慮が抜けていても*エラーにならない*

```typescript
type Cake = {
  name: "ショートケーキ" | "チーズケーキ" | "モンブラン";
  fruit?: string;
};

declare const myCake: Cake;

function getMessage() {
  switch (myCake.name) { // case "モンブラン" がないと明らかに実装漏れ
    case "ショートケーキ":
      return `上は ${myCake.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
  } // ここで『"モンブラン"のcase文がないよ!』みたいなエラーが欲しい
}
```

---

<!-- _class: lead -->

# どうすればいいの?

<div style="position: absolute; bottom: -10px; right: 0">

![w:320](./resources/typescript-faq.webp)

</div>

---

## never型を使って*ExhaustiveErrorエラー*をつくる

```typescript
export class ExhaustiveError extends Error { // 新しく追加したエラークラス
  constructor(value: never, message = `Unsupported type: ${value}`) { // コンストラクタはnever型
    super(message);
  }
}

type Cake = {
  name: "ショートケーキ" | "チーズケーキ" | "モンブラン";
  fruit?: string;
};

declare const myCake: Cake;

function getMessage() {
  switch (myCake.name) { // 1.myCake.nameの型は "ショートケーキ" | "チーズケーキ" | "モンブラン"
    case "ショートケーキ":
      return `上は ${myCake.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
    default: // 2.なのでdefaultに入るのはmyCake.nameが"モンブラン"の場合のみ( = "モンブラン"型と推論)
      return new ExhaustiveError(myCake.name) // ⛔ myCake.name がnever型でない場合はエラーになる ("モンブラン型" なのでエラー)
  }
}
```

<footer>

<div class="flex justify-center gap-8">

[never型](https://www.typescriptlang.org/docs/handbook/2/narrowing.html#the-never-type)

[Exhaustiveness checking](https://www.typescriptlang.org/docs/handbook/2/narrowing.html#exhaustiveness-checking)

</div>

</footer>

---

## swtichのcase文が網羅されていればnever型となる

```typescript
export class ExhaustiveError extends Error
  constructor(value: never, message = `Unsupported type: ${value}`)
    super(message);
  }
}

type Cake = {
  name: "ショートケーキ" | "チーズケーキ" | "モンブラン";
  fruit?: string;
};

declare const myCake: Cake;

function getMessage() {
  switch (myCake.name) { // 1.myCake.nameの型は "ショートケーキ" | "チーズケーキ" | "モンブラン"
    case "ショートケーキ":
      return `上は ${myCake.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
    case "モンブラン": // 追加
      return `モンブランはやっぱり ${myCake.fruit} よね!`;
    default: // 2.なのでdefaultの中には絶対に入らないはず...
      return new ExhaustiveError(myCake.name) // 3.よってmyCake.nameはnever型と推論されるためエラーは消える
  }
}
```

<footer>

<div class="flex justify-center gap-8">

[never型](https://www.typescriptlang.org/docs/handbook/2/narrowing.html#the-never-type)

[Exhaustiveness checking](https://www.typescriptlang.org/docs/handbook/2/narrowing.html#exhaustiveness-checking)

</div>

</footer>

---

<!-- _class: lead -->

# この先不要なコードをカット

---

## まだ問題がある

```typescript
type Cake = {
  name: "ショートケーキ" | "チーズケーキ";
  fruit?: string;
};

declare const myCake: Cake;

function getMessage() {
  switch (myCake.name) {
    case "ショートケーキ":
      return `上は ${myCake.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
    default:
      return new ExhaustiveError(myCake.name);
  }
}
```

---

## ショートケーキのfruitが*イチゴである*と推論してくれない

```typescript
type Cake = {
  name: "ショートケーキ" | "チーズケーキ";
  fruit?: string;
};

declare const myCake: Cake;

function getMessage() {
  switch (myCake.name) {
    case "ショートケーキ":
      return `上は ${myCake.fruit} だ！`; // myCake.fruit は string | undefined型 と推論される
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
    default:
      return new ExhaustiveError(myCake.name);
  }
}
```

---

## 現状の型定義ではこれ以上*Narrowing(型の絞り込み)できない*

```typescript
type Cake = {
  name: "ショートケーキ" | "チーズケーキ";
  fruit?: string;
};

const cakes: Cake[] = [ // 今の定義では以下6パターンのいずれもOKとなってしまう
  { name: "ショートケーキ" }, // エラーにしたい！
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "ショートケーキ", fruit: "マロン" }, // エラーにしたい！
  { name: "チーズケーキ" },
  { name: "チーズケーキ", fruit: "イチゴ" }, // エラーにしたい！
  { name: "チーズケーキ", fruit: "マロン" }, // エラーにしたい！
];
```

<footer>

[Narrowing](https://www.typescriptlang.org/docs/handbook/2/narrowing.html)

</footer>

---

<!-- _class: lead -->

# どうすればいいの?

<div style="position: absolute; bottom: -10px; right: 0">

![w:320](./resources/typescript-faq.webp)

</div>

---

## *判別されたユニオン型*を使う

```typescript
type SpongeCake = {
  name: "ショートケーキ"; // 共通のプロパティ
  fruit: "イチゴ";
};
type Cheesecake = {
  name: "チーズケーキ"; // 共通のプロパティ
};
type Cake = SpongeCake | Cheesecake; // Cakeは判別用の共通プロパティ(name)をもつユニオン型である

const cakes: Cake[] = [
  { name: "ショートケーキ" },
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "ショートケーキ", fruit: "マロン" },
  { name: "チーズケーキ" },
  { name: "チーズケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ", fruit: "マロン" },
];
```

<footer>

[判別されたユニオン型(Discriminated unions)](https://www.typescriptlang.org/docs/handbook/2/narrowing.html#discriminated-unions)

</footer>

---

## SpongeCake型でもCheesecake型でもない値は*エラーになる*

```typescript
type SpongeCake = {
  name: "ショートケーキ";
  fruit: "イチゴ";
};
type Cheesecake = {
  name: "チーズケーキ";
};
type Cake = SpongeCake | Cheesecake;

const cakes: Cake[] = [
  { name: "ショートケーキ" },                  // ⛔ エラーになる (SpongeCake型なのにfruitがない)
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "ショートケーキ", fruit: "マロン" }, // ⛔ エラーになる (.fruitの値が"イチゴ"ではない)
  { name: "チーズケーキ" },
  { name: "チーズケーキ", fruit: "イチゴ" },   // ⛔ エラーになる (Cheesecake型なのにfruitがある)
  { name: "チーズケーキ", fruit: "マロン" },   // ⛔ エラーになる (Cheesecake型なのにfruitがある)
];
```

---

## ショートケーキのfruitが*イチゴである*と推論してくれない

```typescript
type Cake = {
  name: "ショートケーキ" | "チーズケーキ";
  fruit?: string;
};

declare const myCake: Cake;

function getMessage() {
  switch (myCake.name) {
    case "ショートケーキ":
      return `上は ${myCake.fruit} だ！`; // myCake.fruit は string | undefined型 と推論される
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
    default:
      return new ExhaustiveError(myCake.name);
  }
}
```

<span class="tag-note">再掲</span>

---

## 判別されたユニオン型に変更

```typescript
type SpongeCake = {
  name: "ショートケーキ";
  fruit: "イチゴ";
};
type Cheesecake = {
  name: "チーズケーキ";
};
type Cake = SpongeCake | Cheesecake;

declare const myCake: Cake;

function getMessage() {
  switch (myCake.name) { // 1.myCake.name は "ショートケーキ" | "チーズケーキ"型と推論される
    case "ショートケーキ":
      return `上は ${myCake.fruit} だ！`; // 2.myCake.fruit は "イチゴ"型 と推論される！ (myCakeがSpongeCake型と推論されたから)
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
    default: // 3.ここにくるのはあり得ない -> myCake は never型 と推論される
      return new ExhaustiveError(myCake); // myCake.name -> myCake に変更 (詳細は時間の都合で割愛)
  }
}
```

---

<!-- _class: lead -->

# swtich文のフォーカスを解いてみる

---

## これでOK?

```typescript
const cakeList: Cake[] = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
];

type SpongeCake = {
  name: "ショートケーキ";
  fruit: "イチゴ";
};
type Cheesecake = {
  name: "チーズケーキ";
};
type Cake = SpongeCake | Cheesecake;

let myCake: Cake = { name: "チーズケーキ" };
myCake = cakeList[0];

function getMessage() {
  switch (myCake.name) {
    case "ショートケーキ":
      return `上は ${myCake.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
    default:
      return new ExhaustiveError(myCake); // (ExhaustiveErrorの定義は割愛)
  }
}
```

---

<!-- _class: lead -->

# 今度は型定義にフォーカスしてみる

---

## 型定義部分にだけフォーカス

```typescript
const cakeList: Cake[] = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
];

type SpongeCake = {
  name: "ショートケーキ";
  fruit: "イチゴ";
};
type Cheesecake = {
  name: "チーズケーキ";
};
type Cake = SpongeCake | Cheesecake;

let myCake: Cake = { name: "チーズケーキ" };
myCake = cakeList[0];

function getMessage() {
  switch (myCake.name) {
    case "ショートケーキ":
      return `上は ${myCake.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
    default:
      return new ExhaustiveError(myCake); 
  }
}
```

---

## 型定義部分にだけ*フォーカス*

```typescript
const cakeList: Cake[] = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
];

type SpongeCake = {
  name: "ショートケーキ";
  fruit: "イチゴ";
};
type Cheesecake = {
  name: "チーズケーキ";
};
type Cake = SpongeCake | Cheesecake;
```

---

## ケーキの種類を増やしてみる

```typescript
const cakeList: Cake[] = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
  { name: "モンブラン", fruit: "栗" }, // 追加
  { name: "チョコレートケーキ" }, // 追加
];

type SpongeCake = {
  name: "ショートケーキ";
  fruit: "イチゴ";
};
type Cheesecake = {
  name: "チーズケーキ";
};
type MontBlanc = { // 追加
  name: "モンブラン";
  fruit: "栗";
};
type ChocolateCake = { // 追加
  name: "チョコレートケーキ";
};
type Cake = SpongeCake | Cheesecake | MontBlanc | ChocolateCake; // 追加
```

---

<!-- _class: lead -->

# なんか面倒くさくない...?

---

## 候補が決まっているなら変更は最低限にしたい

```typescript
const cakeList = [ // cakeListに追加したらCake型に自動で反映されてほしい
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
];

type Cake = ??? // ここをイイ感じに定義して1行で済ませたい
```

---

<!-- _class: lead -->

# どうすればいいの?

<div style="position: absolute; bottom: -10px; right: 0">

![w:320](./resources/typescript-faq.webp)

</div>

---

## typeof型演算子とインデックスアクセス型を使う

```typescript
const cakeList = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
];

type Cake = (typeof cakeList)[number]; // typeof型演算子でcakeList(値)から型を生成し、[number]でその配列要素の型を表現する
```

<footer>

<div class="flex justify-center gap-8">

[typeof型演算子(Typeof Type Operator)](https://www.typescriptlang.org/docs/handbook/2/typeof-types.html)

[インデックスアクセス型(Indexed Access Types)](https://www.typescriptlang.org/docs/handbook/2/indexed-access-types.html)

</div>

</footer>

---

## *typeof型演算子*とインデックスアクセス型を使う

```typescript
const cakeList = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
];

type Cake = (typeof cakeList)[number]; // typeof型演算子でcakeList(値)から型を生成し、[number]でその配列要素の型を表現する
```

`推論の過程`

<div class="grid-col-5-5" style="align-items: baseline">

```typescript
type (typeof cakeList) = ({ // 配列と推論
    name: string;
    fruit: string;
} | {
    name: string;
    fruit?: undefined;
})[]
```

</div>

<footer>

<div class="flex justify-center gap-8">

[typeof型演算子(Typeof Type Operator)](https://www.typescriptlang.org/docs/handbook/2/typeof-types.html)

[インデックスアクセス型(Indexed Access Types)](https://www.typescriptlang.org/docs/handbook/2/indexed-access-types.html)

</div>

</footer>

---

## *typeof型演算子*と*インデックスアクセス型*を使う

```typescript
const cakeList = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
];

type Cake = (typeof cakeList)[number]; // typeof演算子でcakeList(値)から型を生成し、[number]でその配列要素の型を表現する
```

`推論の過程`

<div class="grid-col-5-5" style="align-items: baseline">

```typescript
type (typeof cakeList) = ({
    name: string;
    fruit: string;
} | {
    name: string;
    fruit?: undefined;
})[]
```

```typescript
type (typeof cakeList)[number] = {
    name: string;
    fruit: string;
} | {
    name: string;
    fruit?: undefined;
}
```

</div>

<footer>

<div class="flex justify-center gap-8">

[typeof型演算子(Typeof Type Operator)](https://www.typescriptlang.org/docs/handbook/2/typeof-types.html)

[インデックスアクセス型(Indexed Access Types)](https://www.typescriptlang.org/docs/handbook/2/indexed-access-types.html)

</div>

</footer>

---

## constは*代入した値を不変にするわけではない*

```typescript
const cakeList = [ // cakeListの値は変更できるため (typeof cakeList)[number]["name"] は string型 よりもNarrowingされない
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
];

type Cake = (typeof cakeList)[number];
```

`推論の過程`

<div class="grid-col-5-5" style="align-items: baseline">

```typescript
type (typeof cakeList) = ({
    name: string;
    fruit: string;
} | {
    name: string;
    fruit?: undefined;
})[]
```

```typescript
type (typeof cakeList)[number] = {
    name: string;
    fruit: string;
} | {
    name: string;
    fruit?: undefined;
}
```

</div>

<footer>

<div class="flex justify-center gap-8">

[typeof型演算子(Typeof Type Operator)](https://www.typescriptlang.org/docs/handbook/2/typeof-types.html)

[インデックスアクセス型(Indexed Access Types)](https://www.typescriptlang.org/docs/handbook/2/indexed-access-types.html)

</div>

</footer>

---

## *as const* で cakeListを*不変*にする

```typescript
const cakeList = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
] as const; // as const を追加

type Cake = (typeof cakeList)[number];
```

<footer>

[as const](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#literal-inference)

</footer>

---

## *as const* で cakeListを*不変*にする

```typescript
const cakeList = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
] as const; // as const を追加

type Cake = (typeof cakeList)[number];
```

`推論の過程`

<div class="grid-col-7-3" style="align-items: baseline">

```typescript
type (typeof cakeList) = readonly [{ // 配列ではなくタプル型に推論される！
    readonly name: "ショートケーキ";
    readonly fruit: "イチゴ";
}, {
    readonly name: "チーズケーキ";
}]
```

</div>

<footer>

[as const](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#literal-inference)

</footer>

---

## *as const* で cakeListを*不変*にする

```typescript
const cakeList = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
] as const; // as const を追加

type Cake = (typeof cakeList)[number];
```

`推論の過程`

<div class="grid-col-5-5" style="align-items: baseline">

```typescript
type (typeof cakeList) = readonly [{
    readonly name: "ショートケーキ";
    readonly fruit: "イチゴ";
}, {
    readonly name: "チーズケーキ";
}]
```

```typescript
type (typeof cakeList)[number] = {
    readonly name: "ショートケーキ";
    readonly fruit: "イチゴ";
} | {
    readonly name: "チーズケーキ";
}
```

</div>

<footer>

[as const](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#literal-inference)

</footer>

---

<!-- _class: lead -->

# 話を戻すと...

---

## ケーキの種類を増やすために必要な型と作業が...

```typescript
const cakeList: Cake[] = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
  { name: "モンブラン", fruit: "栗" }, // 追加
  { name: "チョコレートケーキ" }, // 追加
];

type SpongeCake = {
  name: "ショートケーキ";
  fruit: "イチゴ";
};
type Cheesecake = {
  name: "チーズケーキ";
};
type MontBlanc = { // 追加
  name: "モンブラン";
  fruit: "栗";
};
type ChocolateCake = { // 追加
  name: "チョコレートケーキ";
};
type Cake = SpongeCake | Cheesecake | MontBlanc | ChocolateCake; // 追加
```

---

## 実際はここまでスリム化できる

```typescript
const cakeList: Cake[] = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
  { name: "モンブラン", fruit: "栗" },
  { name: "チョコレートケーキ" },
] as const; // as const 追加

type Cake = (typeof cakeList)[number]; // typeof型演算子とインデックスアクセス型で表現
```

---

## ただ、一部の条件に当てはまる場合に限る

```typescript
const cakeList: Cake[] = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
  { name: "モンブラン", fruit: "栗" },
  { name: "チョコレートケーキ" },
] as const; // as const 追加

type Cake = (typeof cakeList)[number]; // typeof型演算子とインデックスアクセス型で表現
```

- 条件
  - *ビルド時に選択肢(cakeList)が確定している*
    - APIからデータ取得する場合などは使えない
  - `Cheesecake型`など個々の型を利用することがない
    - 個々の型を利用するなら**判別されたユニオン型**を使った方がいい

---

<!-- _class: lead -->

# Vueファイルに適当してみよう

---

## TypeScriptのコードのみ (before)

```typescript
<script setup lang="ts">
import { computed, ref } from "vue";

const cakeList = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
];

const myCake = ref<any>("");

const message = computed(() => {
  switch (myCake.value.name) {
    case "ショートケーキ":
      return `上は ${myCake.value.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
  }
});
</script>
```

---

## TypeScriptのコードのみ (after)

```typescript
<script setup lang="ts">
import { computed, ref } from "vue";
import { ExhaustiveError } from "./errors"; // ExhaustiveErrorは外部からimport

const cakeList = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
] as const; // as const 追加
type Cake = (typeof cakeList)[number]; // Cake型の定義追加

const myCake = ref<Cake>(cakeList[0]); // 初期値を挿入

const message = computed(() => {
  switch (myCake.value.name) {
    case "ショートケーキ":
      return `上は ${myCake.value.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
    default: // defaultとExhaustiveErrorによる網羅性チェックを追加
      return new ExhaustiveError(myCake.value);
  }
});
</script>
```

---

## 全体

<div class="grid-col-5-5" style="align-items: baseline">

```typescript
<script setup lang="ts">
import { computed, ref } from "vue";
import { ExhaustiveError } from "./errors";

const cakeList = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
] as const;
type Cake = (typeof cakeList)[number];

const myCake = ref<Cake>(cakeList[0]);

const message = computed(() => {
  switch (myCake.value.name) {
    case "ショートケーキ":
      return `上は ${myCake.value.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
    default:
      return new ExhaustiveError(myCake.value);
  }
});
</script>
```

<div>

```html
<template>
  <select v-model="myCake">
    <option v-for="cake in cakeList" :value="cake">
      {{ cake.name }}
    </option>
  </select>
  <h1>{{ message }}</h1>
</template>
```

```typescript
-- src/errors.ts
export class ExhaustiveError extends Error {
  constructor(
    value: never,
    message = `Unsupported type: ${value}`
  ) {
    super(message);
  }
}
```

</div>

</div>

---

## まとめ

- *文字列リテラルのユニオン型*を使って候補をstringより**Narrowing**しよう
- *ExhausitiveError*を使って**caseの実装漏れ**を防ごう
- **可変候補**には *判別されたユニオン型*を使って**Narrowing**しよう (APIなど)
- **固定候補**には *typeof型演算子 + インデックスアクセス型 + as const* を使おう

<div style="position: absolute; bottom: -10px; right: 0">

![w:320](./resources/typescript-stand-smile.webp)

</div>

<h5 class="text-primary" style="position: absolute; bottom: 180px; right: 280px; transform: rotate(4deg)">
   ご感想・ご質問 お待ちしてまーす
</h5>
