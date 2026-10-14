---
title: "【実践】HTML / CSS / JavaScript を実際に書いて動かしてみよう！"
emoji: "💻"
type: "tech"
topics: ["html", "css", "javascript", "codepen", "beginner"]
published: true
---

前回の記事でHTML、CSS、JavaScriptの基本を学びました。今回は、**実際に手を動かして簡単な「カウンターアプリ（ボタンを押すと数字が増える仕組み）」を作ってみましょう！**

環境構築をせずに、ブラウザ上ですぐに試せる方法も紹介します。

---

## 💻 準備：どこでコードを書く？

一番簡単なのは、ブラウザだけでコードが書けてその場で動きが見える無料サービス [CodePen](https://codepen.io) や [JSFiddle](https://jsfiddle.net) を使う方法です。
PCのローカル環境で作る場合は、VS Codeなどのエディタで `index.html` というファイルを作って開くだけでOKです。

---

## 🛠️ 実際に書くコード

以下のHTML、CSS、JavaScriptをそれぞれ組み合わせて動かしてみましょう。

### 1. HTML（構造を作る）
画面に表示する「現在の数字」と、数字を増やすための「ボタン」を配置します。

```html
<div class="counter-container">
  <h1>カウンター</h1>
  <!-- 数字を表示する場所（初期値は0） -->
  <div id="counter-value">0</div>
  <!-- クリックするためのボタン -->
  <button id="increment-btn">＋ カウントアップ</button>
</div>
```

### 2. CSS（見た目を整える）
中央寄せにして、数字を大きく見せ、ボタンのクリック感をデザインします。

```css
/* 画面全体を中央寄せにする */
body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #f0f2f5;
  margin: 0;
  font-family: sans-serif;
}

/* カウンター全体の枠 */
.counter-container {
  text-align: center;
  background: white;
  padding: 30px;
  border-radius: 12px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

/* 大きく表示する数字 */
#counter-value {
  font-size: 64px;
  font-weight: bold;
  color: #333;
  margin: 20px 0;
}

/* ボタンのデザイン */
button {
  background-color: #10b981; /* 緑色 */
  color: white;
  border: none;
  padding: 12px 24px;
  font-size: 18px;
  border-radius: 8px;
  cursor: pointer;
  transition: background 0.2s;
}

/* ボタンにマウスを乗せたとき */
button:hover {
  background-color: #059669;
}
```

### 3. JavaScript（動きをつける）
ボタンが押されたら「数字をカウントして、画面を書き換える」という処理を記述します。

```javascript
// 1. HTMLの要素（数字が表示されている場所とボタン）をJavaScriptで取得する
const counterValue = document.getElementById('counter-value');
const incrementBtn = document.getElementById('increment-btn');

// 2. カウントした数字を記憶しておく変数（最初は0）
let count = 0;

// 3. ボタンがクリックされたときの動きを登録する
incrementBtn.addEventListener('click', () => {
  // 数字を1ずつ増やす
  count = count + 1; 
  
  // 増えた新しい数字を、HTMLの画面上に書き換えて表示する
  counterValue.textContent = count;
});
```

---

## 🔍 コードの解説とポイント

### HTMLの `id` 属性
JavaScriptやCSS側から「あのボタンを動かしたい」「あの数字の場所の色を変えたい」とピンポイントで指定するために、HTMLには `id="increment-btn"` のような**固有の名前（背番号のようなもの）**をつけておきます。

### JavaScriptの `textContent`
JavaScriptで計算した結果を、HTMLの文字として画面に反映させるために `textContent` という命令を使っています。これによって、ボタンを押すたびに画面の「0」が「1」「2」「3」へとリアルタイムに変化します。

---

## 🎉 まとめ

1. **HTML** で要素を置き、`id` で名前をつける
2. **CSS** でサイズや配置、心地よいデザインに整える
3. **JavaScript** で要素を取得し、イベント（クリックなど）に合わせて画面を書き換える

この3ステップの組み合わせが、どんなに複雑なWebアプリケーションでも基本の形になります。まずはここから色々なパーツを動かしてみてください！
