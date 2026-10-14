---
title: "HTML / CSS / JavaScript の基本的な使い方まとめ"
emoji: "🌐"
type: "tech"
topics: ["html", "css", "javascript", "beginner"]
published: true
---

WebサイトやWebアプリを形作る、最も基本となる3つの言語（HTML・CSS・JavaScript）の役割と基本的な使い方をシンプルにまとめました。

---

## 1. 3つの言語の役割（イメージ）

よく「家づくり」や「人間」に例えられます。

* **HTML**：骨組み・構造（壁、ドア、窓を配置する）
* **CSS**：見た目・デザイン（壁紙を貼る、色を塗る、サイズを整える）
* **JavaScript**：動き・機能（ドアを開け閉めする、電気をつける）

---

## 2. HTML（エイチ・ティー・エム・エル）
Webページの**骨組み（文章構造）**を作ります。`<>` で囲まれた「タグ」を使って文字や画像を挟みます。

```html
<!-- 基本的なタグの例 -->
<h1>これは一番大きな見出しです</h1>
<p>これは段落（普通の文章）です。</p>
<a href="https://zenn.dev">Zennへのリンクです</a>
<button id="myButton">クリックしてね</button>
```

---

## 3. CSS（シー・エス・エス）
HTMLで作った骨組みに対して、**色、サイズ、配置などのデザイン**を指定します。

```css
/* 文字の色やボタンの見た目を変える例 */
h1 {
  color: #333333; /* 文字の色を濃いグレーに */
  font-size: 24px; /* 文字の大きさを24ピクセルに */
}

button {
  background-color: #007bff; /* ボタンの背景を青色に */
  color: white; /* ボタンの文字を白に */
  padding: 10px 20px; /* 内側に余白を作る */
  border: none; /* 枠線を消す */
  border-radius: 5px; /* 角を少し丸くする */
}
```

---

## 4. JavaScript（ジャバスクリプト）
Webページに**動的な機能やクリックしたときの処理**を追加します。

```javascript
// ボタンをクリックしたときにメッセージを出す例
const button = document.getElementById('myButton');

button.addEventListener('click', () => {
  alert('ボタンがクリックされました！');
});
```

---

## 5. 1つのファイルにまとめる場合の全体像
実際の開発ではファイルを分けきることが多いですが、基礎を学ぶときは以下のように1つのHTMLファイルにまとめて書くこともできます。

```html
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <title>初めてのWebページ</title>
  <style>
    /* ここにCSSを書く */
    body { font-family: sans-serif; text-align: center; margin-top: 50px; }
    h1 { color: #007bff; }
  </style>
</head>
<body>

  <h1>Hello World!</h1>
  <button id="btn">ここを押してね</button>

  <script>
    // ここにJavaScriptを書く
    document.getElementById('btn').addEventListener('click', () => {
      alert('こんにちは！');
    });
  </script>
</body>
</html>
```

これらの3つを組み合わせることで、普段私たちが使っているすべてのWebサイトが作られています。
