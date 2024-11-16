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
  <div>実戦 型パズル</div>
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
      <span>TypeScript >> Python = Go = Rust >> Lua</span>
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

<!-- _class: lead -->

## よくあるVueのSelector実装を通して

## 実戦で使えるTypeScriptの型スキルを学ぼう

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

let myCake: any = ""; // myCakeをany型と宣言
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

---

## *Cake型*を定義し、変数myCakeの型は*Cake型*だと宣言する

```typescript
const cakeList = [ "ショートケーキ", "チーズケーキ" ];

type Cake = { // Cake型の宣言
  name: string;   // 名前は必須
  fruit?: string; // フルーツが乗ってるかも?
}

let myCake: Cake = { name: "ショートケーキ" }; // any -> Cake に変更して、初期値も設定
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

let myCake: Cake = { name: "ショートケーキ" };
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

# ウォーミングアップは終わりだ

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

let myCake: Cake = { name: "ショートケーキ" };
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

let myCake: Cake = { name: "ショートケーキ" };
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

let myCake: Cake = { name: "ショートケーキ" };
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

let myCake: Cake = { name: "ショートケーキ" };
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

let myCake: Cake = { name: "ショートケーキ" }; // 2.myCakeはCake型 (let宣言なので右辺の値は関係ない)
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

let myCake: Cake = { name: "ショートケーキ" };
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

let myCake: Cake = { name: "ショートケーキ" };
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

let myCake: Cake = { name: "ショートケーキ" };
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

---

## never型を使ってExhaustiveErrorエラーをつくる

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

## ショートケーキのイチゴが必ず乗っていると認識してくれない

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

## ショートケーキのイチゴが必ず乗っていると認識してくれない

```typescript
type Cake = {
  name: "ショートケーキ" | "チーズケーキ";
  fruit?: string; // fruit? なので string | undefined型 と宣言されている
};

declare const myCake: Cake;

function getMessage() {
  switch (myCake.name) {
    case "ショートケーキ":
      return `上は ${myCake.fruit} だ！`; // myCake.fruit は "イチゴ"型... せめて string型 と推論してほしい
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

---

<!-- _class: lead -->

# どうすればいいの?

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

---

## SpongeCake型でもCheesecake型でもない値はエラーになる

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

## (再掲)

```typescript
type Cake = {
  name: "ショートケーキ" | "チーズケーキ";
  fruit?: string; // fruit? なので string | undefined型 と宣言されている
};

declare const myCake: Cake;

function getMessage() {
  switch (myCake.name) {
    case "ショートケーキ":
      return `上は ${myCake.fruit} だ！`; // myCake.fruit は "イチゴ"型... せめて string型 と推論してほしい
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
    default:
      return new ExhaustiveError(myCake.name);
  }
}
```

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

## constは変数への*再代入*を禁止するだけ

```typescript
const cakeList = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
];

cakeList = []; // ⛔ これはエラー

cakeList[0] = { name: "チョコレートケーキ" }; // これはOK
cakeList[0].name = "チョコレートケーキ"; // これはOK
```

`cakeList[0]["name"]` は `string型` であるとしか言えない

---

<!-- _class: lead -->

# そんな貴方に as const

---

## as constは*変数に代入した値そのものを変更不可にする*

```typescript
const cakeList = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
] as const; // as const を追加

cakeList = []; // ⛔ これはエラー

cakeList[0] = { name: "チョコレートケーキ" }; // ⛔ これもエラー
cakeList[0].name = "チョコレートケーキ"; // ⛔ これもエラー
```

つまり`cakeList[0]["name"]` は `"ショートケーキ"型` であると言える

---

## as constを適応してみる

```typescript
const cakeList = [
  { name: "ショートケーキ", fruit: "イチゴ" },
  { name: "チーズケーキ" },
] as const; // as const を追加

type Cake = {
  name: "ショートケーキ" | "チーズケーキ";
  fruit?: string;
};

let myCake: Cake = { name: "ショートケーキ" };
myCake = cakeList[0]; // 1.{ readonly name: "ショートケーキ"; readonly fruit: "イチゴ"; }型 と推論される

function getMessage() {
  switch (myCake.name) { // 2.myCake.nameの値は "ショートケーキ" or "チーズケーキ"
    case "ショットケーキ":// ⛔ 3.ここも無事エラーになる
      return `上は ${myCake.fruit} だ！`;
    case "チーズケーキ":
      return `チーズケーキおいしい!`;
  }
}
```

---

<!-- _class: lead -->

# どうすればいいか?

---
