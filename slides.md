---
theme: default
title: V が名前に入ってる
info: |
  ## 「V が名前に入ってる」
  学生と社会人LT会 2024.09.07
class: text-right
transition: slide-left
fonts:
  sans: "Kosugi Maru"
  mono: "Fira Code"
---

<h1>V <span v-click>が名前に入ってる</span></h1>

<div first-letter:text-blue>ナイトウ <a href="https://twitter.com/engineer_naito" target="_blank" rel="noopener noreferrer"><carbon-logo-twitter /></a></div>

<div class="pt-12 first-letter:text-blue">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 first-letter:text-blue">
  {{ nowStrRef }}
</div>

<script setup lang="ts">
import { ref, onMounted } from "vue";

const now = new Date();
const nowStr = now.toLocaleString();
const nowStrRef = ref(nowStr);

function tick() {
  const newTime = new Date();
  const newTimeStr = newTime.toLocaleString();
  nowStrRef.value = newTimeStr;
}

onMounted(() => {
  setInterval(tick, 1000);
  tick();
})
</script>

<style>
h1::first-letter {
  color: green;
  font-size: 300%;
}
</style>

---
title: slide-link
level: 2
---

<h1>こ<span text-blue>の</span>スライドはこちらで</h1>

<div
  mt-10
  flex="~ col"
  gap-16
  justify-center
  items-center
>
  <input v-model="text" type="text" w-full />
  <img :src="qrcode" alt="QR Code" w-64/>
</div>

<script setup>
import { ref } from "vue";
import { useQRCode } from "@vueuse/integrations/useQRCode";

const text = ref("まだデプロイしてない");
const qrcode = useQRCode(text);
</script>

---
transition: fade
---

<h1>Table <span text-blue>o</span>f contents</h1>

<Toc v-click minDepth="1" maxDepth="1"></Toc>

---
transition: slide-left
title: 自己紹介
layout: two-cols
layoutClass: gap-16
---

<img src="/images/green_heart.png" />

<ul>
  <li>
    <a href="https://twitter.com/engineer_naito" target="_blank" rel="noopener noreferrer">
      <carbon-logo-twitter text-blue /> 旧 Twitter <carbon-new-tab />
    </a>
  </li>
  <li>
    <a href="https://github.com/kosuke222naito" target="_blank" rel="noopener noreferrer">
      <carbon-logo-github text-blue /> GitHub <carbon-new-tab />
    </a>
  </li>
  <li>
    <a href="https://zenn.dev/kosuke_naito" target="_blank" rel="noopener noreferrer">
      <carbon-blog text-blue /> Zenn <carbon-new-tab />
    </a>
  </li>
</ul>

<br />

<Tweet
  id="1764917140338147519"
  scale="0.6"
  v-click="2"
/>

::right::

<h1>
  <span class="text-gradation">I'm ナイトウ</span>
</h1>

<ul class="text-2xl">
  <li v-click>
    <span class="color-python">Python</span> <carbon-logo-python text-blue /> で Web バックエンド
  </li>
  <li v-click>Web フロントもやりたい</li>
  <li v-after><span class="text-gradation">Vue</span> <carbon-logo-vue text-green /> が好き</li>
  <li v-click>since: 2021 (<span text-blue>{{ years }}</span>年目)</li>
  <li v-after><span class="color-itf">筑波大</span>卒 (非 CS 専攻)</li>
  <li v-click><span text-yellow>柏</span> (<a href="https://toukatsu.connpass.com/">東葛de<span text-green>v</span></a> 運営)</li>
  <li v-click>自作キーボード</li>
</ul>

<script setup lang="ts">
import { ref } from "vue";
const now = new Date();
const START_DATE = new Date(2021, 1, 1);
const years = now.getFullYear() - START_DATE.getFullYear() + 1;
</script>

<style>
.text-gradation {
  background: linear-gradient(45deg, #52D422, #2266D4);
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-size: 400% 400%;
}

h1 span.text-gradation {
  animation: GradientBackground 3s ease infinite;
}

ul li span.text-gradation {
  animation: GradientBackground 5s ease infinite;
}

.color-python {
  background: linear-gradient(45deg, #3776AB, #FFD43B);
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-size: 400% 400%;
  animation: GradientBackground 5s ease infinite;
}

.color-itf {
  background: linear-gradient(45deg, #00BFD6, #6600CC);
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-size: 400% 400%;
  animation: GradientBackground 5s ease infinite;
}

@keyframes GradientBackground {
  0% {
    background-position: 0% 50%;
  }

  50% {
    background-position: 100% 50%;
  }

  100% {
    background-position: 0% 50%;
  }
};
</style>

---
transition: view-transition
title: V が名前に入ってる技術
---

<h1><span class="emphasized-V">V</span></h1>

<style>
@view-transition {
  navigation: auto;
}

h1 {
  margin-top: 300px;
  margin-left: 600px;
}

.emphasized-V {
  view-transition-name: emphasized-V;
  font-size: 400px;
  background: linear-gradient(45deg, #52D422, #2266D4);
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-size: 400% 400%;
  animation: GradientBackground 3s ease infinite;
}

@keyframes GradientBackground {
  0% {
    background-position: 0% 50%;
  }

  50% {
    background-position: 100% 50%;
  }

  100% {
    background-position: 0% 50%;
  }
};
</style>

---
transition: slide-left
layout: cover
class: text-left text-8xl
---

<span class="text-green emphasized-V">V</span>ue

<style>
.emphasized-V {
  view-transition-name: emphasized-V;
}
</style>

---
transition: slide-down
layout: cover
class: text-center text-7xl
---

Slide<span class="text-green">v</span>

---
transition: slide-right
layout: cover
class: text-right text-9xl
---

u<span class="text-green">v</span>

---
transition: slide-up
layout: cover
class: text-left text-8xl
---

<span class="text-green">V</span>S Code

---
transition: slide-left
layout: cover
class: text-center text-7xl
---

<span class="text-green">V</span>ite

---
transition: slide-down
layout: cover
class: text-right text-9xl
---

<span class="text-green">V</span>ercel

---
transition: slide-right
layout: cover
class: text-center text-8xl
---

S<span class="text-green">v</span>elte

---
transition: slide-up
layout: cover
class: text-left text-7xl
---

<span class="text-green">V</span>olta

---
transition: slide-down
layout: cover
class: text-right text-8xl
---

<span class="text-green">V</span>agrant

---
transition: slide-left
layout: cover
class: text-center text-9xl
---

Hyper-<span class="text-green">V</span>

---
transition: slide-up
layout: cover
class: text-left text-7xl
---

<span class="text-green">V</span>im

---
transition: slide-right
layout: cover
class: text-center text-8xl
---

Ja<span class="text-green">v</span>a

---
transition: slide-down
layout: cover
class: text-right text-9xl
---

Ja<span class="text-green">v</span>aScript

---
transition: slide-left
layout: cover
class: text-left text-8xl
---

n<span class="text-green">v</span>m

---
transition: slide-up
layout: cover
class: text-center text-9xl
---

<span class="text-green">V</span>8

---
transition: slide-right
layout: cover
class: text-right text-7xl
---

<span class="text-green">v</span>0

---
transition: slide-left
layout: cover
class: text-left text-9xl
---

<span class="text-green">V</span>alibot

---
transition: slide-up
layout: cover
class: text-center text-7xl
---

Lara<span class="text-green">v</span>el

---
transition: view-transition
layout: cover
class: text-right text-8xl
---

<span class="text-green emphasized-V">V</span>lang

<style>
.emphasized-V {
  view-transition-name: emphasized-V;
}
</style>

---
transition: fade-out
layout: two-cols-header
---

<h1><span class="emphasized-V text-green text-9xl">V</span></h1>

::left::

<ul>
  <li v-for="item in itemsLeft" :key="item">
    <span v-html="highlightV(item)"></span>
  </li>
</ul>

::right::

<ul>
  <li v-for="item in itemsRight" :key="item">
    <span v-html="highlightV(item)"></span>
  </li>
</ul>

<script setup lang="ts">
import { ref } from "vue";

const itemsLeft = ref([
  "Vue",
  "Slidev",
  "uv",
  "VS Code",
  "Vite",
  "Vercel",
  "Svelte",
  "Volta",
  "Vagrant",
  "Hyper-V"
]);

const itemsRight = ref([
  "Vim",
  "Java",
  "JavaScript",
  "nvm",
  "V8",
  "v0",
  "Valibot",
  "Laravel",
  "Vlang"
]);

const highlightV = (text) => {
  return text.replace(/(v|V)/g, '<span class="text-green">$1</span>');
};
</script>

<style>
@view-transition {
  navigation: auto;
}

.emphasized-V {
  view-transition-name: emphasized-V;
}
</style>

---
transition: view-transition
level: 2
---

<h1>今日<span text-blue>は</span>その中でもこれを</h1>

<br />
<br />
<br />

<ul text-4xl>
  <li><span class="view-transition-slidev">Slide<span class="text-green">v</span></span></li>
  <li><span class="text-green">V</span>ue</li>
  <li>u<span class="text-green">v</span></li>
</ul>

<style>
.view-transition-slidev {
  view-transition-name: view-transition-slidev;
}
</style>

---
transition: fade-out
title: What is Slidev?
---

<h1><span class="view-transition-slidev">Slide<span text-green>v</span></span></h1>

<br />
<br />
<br />

- 📝 **テ<span text-blue>キ</span>ストベース** - Markdown と HTML, CSS のいいとこどり
- 🧑‍💻 **<span text-blue>開</span>発者フレンドリー** - Web の知識がそのまま転用できる
- 🤹 **インタラクティ<span text-blue>ブ</span>** - <span text-green>V</span>ue コンポーネントを埋め込み可能
- 🎥 **録画<span text-blue>機</span>能** - 録画機能とカメラビューもある
- 📤 **<span text-blue>ポ</span>ータブル** - PDF、PPTX、PNG、または SPA としてエクスポート可能
- 🛠 **ハッカブ<span text-blue>ル</span>** - Web でできることはほぼ全てSlide<span text-green>v</span>でも可能

<br />
<br />
<br />

[Why Slidev?](https://sli.dev/guide/why)

<style>
.view-transition-slidev {
  view-transition-name: view-transition-slidev;
}
</style>

---
transition: slide-up
level: 2
---

<h1>このス<span text-blue>ラ</span>イドも</h1>

<div flex justify-center items-center gap-50 h-full text-4xl>
  <div v-click>Powered by <span v-mark="{ at: '2', color: 'green' }">Slide<span text-green>v</span></span></div>
  <img
    v-after
    src="https://sli.dev/logo.png"
    v-motion
    :initial="{ x: -80, opacity: 0}"
    :enter="{ x: 0, opacity: 1, transition: { delay: 1000, duration: 1000 } }"
  />
</div>

---
transition: fade-out
level: 2
---

<h1>クリック<span text-blue>ア</span>ニメーション</h1>

<div v-click>

クリックすると現れる

```html
<div v-click>クリックすると現れる</div>
```

</div>

<br>

<v-click>

<span v-mark.red="3"><code>v-mark</code> ディレクティブ</span>は
<span v-mark.circle.orange="4">インラインマーカー</span>

(Powered by [Rough Notation](https://roughnotation.com/))

```html
<span v-mark.underline.orange>inline markers</span>
```

</v-click>

<div mt-20 v-click>

[Learn more](https://sli.dev/guide/animations#click-animation)

</div>

---
level: 2
---

<h1>Shiki <span text-blue>M</span>agic Mo<span text-green>v</span>e</h1>

Powered by [shiki-magic-move](https://shiki-magic-move.netlify.app/)

<br />

````md magic-move {lines: true}
```ts {*|2|*}
// step 1
const author = reactive({
  name: "John Doe",
  books: [
    "Vue 2 - Advanced Guide",
    "Vue 3 - Basic Guide",
    "Vue 4 - The Mystery",
  ],
});
```

```ts {*|1-2|3-4|3-4,8}
// step 2
export default {
  data() {
    return {
      author: {
        name: "John Doe",
        books: [
          "Vue 2 - Advanced Guide",
          "Vue 3 - Basic Guide",
          "Vue 4 - The Mystery",
        ],
      },
    };
  },
};
```

```ts
// step 3
export default {
  data: () => ({
    author: {
      name: "John Doe",
      books: [
        "Vue 2 - Advanced Guide",
        "Vue 3 - Basic Guide",
        "Vue 4 - The Mystery",
      ],
    },
  }),
};
```

```vue
<!-- step 4 -->
<script setup>
const author = {
  name: "John Doe",
  books: [
    "Vue 2 - Advanced Guide",
    "Vue 3 - Basic Guide",
    "Vue 4 - The Mystery",
  ],
};
</script>
```
````

---

<h1>Motio<span text-blue>n</span>s</h1>

Powered by [@vueuse/motion](https://motion.vueuse.org/)

```html
<div
  v-motion
  :initial="{ x: -80 }"
  :enter="{ x: 0 }"
  :click-3="{ x: 80 }"
  :leave="{ x: 1000 }"
>
  Slidev
</div>
```

<div class="w-60 relative">
  <div class="relative w-40 h-40">
    <img
      v-motion
      :initial="{ x: 800, y: -100, scale: 1.5, rotate: -50 }"
      :enter="final"
      class="absolute inset-0"
      src="https://sli.dev/logo-square.png"
      alt=""
    />
    <img
      v-motion
      :initial="{ y: 500, x: -100, scale: 2 }"
      :enter="final"
      class="absolute inset-0"
      src="https://sli.dev/logo-circle.png"
      alt=""
    />
    <img
      v-motion
      :initial="{ x: 600, y: 400, scale: 2, rotate: 100 }"
      :enter="final"
      class="absolute inset-0"
      src="https://sli.dev/logo-triangle.png"
      alt=""
    />
  </div>

  <div
    class="text-5xl absolute top-14 left-40 text-[#2B90B6] -z-1"
    v-motion
    :initial="{ x: -80, opacity: 0}"
    :enter="{ x: 0, opacity: 1, transition: { delay: 2000, duration: 1000 } }">
    Slidev
  </div>
</div>

<script setup lang="ts">
const final = {
  x: 0,
  y: 0,
  rotate: 0,
  scale: 1,
  transition: {
    type: 'spring',
    damping: 10,
    stiffness: 20,
    mass: 2
  }
}
</script>

<div
  v-motion
  :initial="{ x:35, y: 30, opacity: 0}"
  :enter="{ y: 0, opacity: 1, transition: { delay: 3500 } }">

[Learn more](https://sli.dev/guide/animations.html#motion)

</div>

---
transition: slide-up
---

<h1>Dragga<span text-blue>b</span>le Elements</h1>

<img v-drag="[421,88,345,345]" src="https://sli.dev/logo.png">

<v-drag pos="664,414,261,\_,-15"undefinedundefinedundefinedundefinedundefinedundefinedundefinedundefinedundefinedundefinedundefinedundefinedundefinedundefinedundefined>

  <div text-center text-3xl border border-main rounded text-green>
    Double-click me!
  </div>
</v-drag>

<v-drag-arrow pos="111,348,253,46" two-way />

---

<h1>Monaco <span text-blue>E</span>ditor</h1>

<br />
<br />

```ts {monaco-run}
import { version } from "vue";
import { emptyArray } from "./external";

console.log(`vue ${version}`);
console.log(
  emptyArray<number>(10).reduce(
    (fib) => [...fib, fib.at(-1)! + fib.at(-2)!],
    [1, 1],
  ),
);
```

---
layout: center
class: text-center text-4xl
level: 2
---

# Learn More

[Documentation](https://sli.dev) · [GitHub](https://github.com/slidevjs/slidev) · [Showcases](https://sli.dev/resources/showcases)

<PoweredBySlidev mt-10 />

---
layout: cover
class: text-right
transition: slide-up
---

<h1><span text-green>V</span>ue</h1>

---
layout: iframe-right
url: https:/ja.vuejs.org/about/community-guide
title: Vue コミュニティ
---

<h1><span text-green>V</span>ue コミ<span text-blue>ュ</span>ニティ</h1>

あなたもすでにコミュニティの一員！？

<span text-blue>で</span>きること

- 仲<span text-blue>間</span>のユーザーを助ける
- issue のトリアージ<span text-blue>を</span>助ける
- コー<span text-blue>ド</span>の貢献
- 経験を共<span text-blue>有</span>する
- ドキュメントを翻訳す<span text-blue>る</span>
- コミュニ<span text-blue>テ</span>ィのリーダーになる

---
transition: slide-up
title: 「コミュニティとはグラデーション」
---

<h1><span text-blue>「</span>コミュニティとはグラデーション<span text-blue>」</span></h1>

[【初学者にこそ伝えたい】Vue.js コミュニティ入門](https://zenn.dev/comm_vue_nuxt/articles/vue-community) より引用

<div flex justify-center items-center>
  <img src="/images/vue_community_gradation.png" h-400px />
</div>

---
transition: slide-up
---

<h1>ぼくがやってる<span text-blue>こ</span>と</h1>

<span text-green>V</span>ue 書いてなくてもできることはある

<br />

- <span text-green>v</span>-tokyo <span text-blue>参</span>加
- <span text-green>V</span><span text-blue>u</span>e 教えてもらう(勉強会を開く)
- ドキュメント<span text-blue>日</span>本語訳の改善
- <span text-green>V</span>ue Fes Japan のボランティ<span text-blue>ア</span>
- 記事<span text-blue>を</span>書く
- Twitter, Discord でわち<span text-blue>ゃ</span>わちゃする

---
transition: slide-left
---

<h1>コミュニ<span text-blue>テ</span>ィ</h1>

世界中の <span text-blue>V</span>ue カンファレンス

<div grid grid-cols-5 gap-48 items-center >
  <Tweet id="1582391536318173184" scale="0.7" h-64 />
  <Tweet id="1762760127625531481" scale="0.7" h-16 />
  <Tweet id="1718194948376596941" scale="0.7" h-64 />
  <Tweet id="1182324722316562432" scale="0.7" h-16 />
</div>

---
transition: slide-up
---

<h1><span text-blue>u</span><span text-green>v</span></h1>

Rust 製 Python 用パッケージ & プロジェクトマネージャー

<br />

<div flex gap-50px items-center>
  以下を置き換えるツール
  <a href="https://docs.astral.sh/uv/" target="_blank" rel="noopener noreferrer"><img src="/images/uv_logo.svg" /></a>
</div>

<br />

- `pip`
- `pip-tools`
- `pipx`
- `poetry`
- `pyenv`
- `virtualenv`
- etc...

---
transition: slide-up
---

<h1>Python やるなら u<span text-green>v</span> だけでよくなる<span text-blue >？</span></h1>

よさそうな感じがめちゃする

- Rust 製で高速
- Python 自体のインストール & バージョン管理
- Python パッケージ管理
- Python スクリプトの実行
- プロジェクト管理
- ツール管理
- 慣れ親しんだ pip インターフェースもある
- uv 自体のアップデートなど各種ユーティリティ

---
transition: slide-up
---

<h1>これまでの Py<span text-blue>t</span>hon パッケージツール</h1>

乱世、混沌、錯綜、、、

<br />

<v-clicks>

- どのツールもメリデメがある
  - pip: シンプル but 依存関係管理が困難
  - poetry: 依存関係 & プロジェクト管理 but 速くない
- 併用するとコンフリクトしたり
- 互換性なかったり

</v-clicks>

<v-click>

最も厄介なのは依存関係管理に `requirements.txt` が使われていたこと
(昔はこれで事足りていたはず)
</v-click>

<v-clicks>

- バージョンの固定(.lock)ができない
- 手動で管理
- 複数環境(`dev`, `staging`, `prod`)の管理が難しい

</v-clicks>

---
transition: slide-up
---

<h1>pyprojec<span text-blue>t</span>.toml & .lock ファイル</h1>

モダンなパッケージ管理へ

<v-clicks>

- `.lock` ファイルでバージョン固定
- ツールが `pyproject.toml` を読んで自動的に依存関係の解決
- `.toml` だからパッケージ管理とプロジェクト管理も
- 開発依存とプロダクション依存を分離して管理可能に

</v-clicks>

---
transition: slide-up
layout: two-cols-header
---

<h1>Rye の登<span text-blue>場</span> <a href="https://rye.astral.sh/" target="_blank" rel="noopener noreferrer"> <simple-icons-rye /></a></h1>

パッケージ & プロジェクト管理

::left::

<Tweet id="1649903576750104576" scale="0.5" />

::right::

<v-clicks>

- <div>mitsuhiko さん <a href="https://twitter.com/mitsuhiko" target="_blank" rel="noopener noreferrer"><carbon-logo-twitter /></a> <a href="https://github.com/mitsuhiko" target="_blank" rel="noopener noreferrer"><carbon-logo-github /></a> が自分のために開発</div>
- デフォルトの依存関係なし
- `virtualenv` を利用
- `uv` を採用
- OS ごとの Python を利用しない
- 標準化された `indygreg` Python ビルドを利用
- `pyproject.toml` に依存関係 & プロジェクト設定
- `pyproject.toml` を見てよしなに Python 環境

</v-clicks>

<br />

<v-click>
Rye 自体が優れた機能を提供しているのではなく、
</v-click>

<br />

<span v-click v-mark.yellow>
エコシステムのツールに委譲している。
</span>

---
transition: slide-up
layout: two-cols-header
---

<h1>u<span text-green>v</span></h1>

Rust 製高速 Python パッケージインストーラー & リゾルバー

::left::

<Tweet id="1758252944409956675" scale="0.5" />

::right::

<v-clicks>

- [Ruff](https://astral.sh/ruff) を手がける [astral](https://astral.sh/) 社製
- `pip`, `pip-tools` を代替する簡単なツール
- `virtualenv` の代わりも
- 高速
- `pip` のインターフェース
- Python に依存していないバイナリ
- グローバル Python のバージョンに依存しない

</v-clicks>

---
transition: slide-left
---

<h1>Rye & u<span text-green>v</span></h1>

`Rye` も astral 社へ

<v-clicks>

- `Rye` と `uv` は目指している地点が近かった
- `Rye` 作者と astral 社の話し合いのもと、
- astral 社で `Rye` を管理することに！
- そして最終的には `uv` と `Rye` が一つになって、
- 完全体 "cargo for Python" へ！

</v-clicks>

---
layout: two-cols
---

<h1>ま<span text-blue>と</span>め</h1>

名前に v って入ってること多くない？

<br />

<div text-2xl>

- Slide<span text-green>v</span> <logos-slidev /> で一緒に遊ぼう！
- <span text-green>V</span>ue <logos-vue animate-ping /> Fes Japan 2024
- 時代はやっぱり Rust <skill-icons-rust /> <v-click>かも？</v-click>

</div>

::right::

<Tweet id="1718194948376596941"/>
