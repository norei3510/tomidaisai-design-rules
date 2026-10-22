# カード

> v0.3.0: 当日ページでは、情報のまとまりをカードではなく罫線と白い帯で区切る（`guidelines/FOUNDATIONS.md` §5.1）。カードを使うのは §1 の「サイン板」と §2 の「押せる1件」だけ。§4・§5 は来場者企画との互換。

## 1. サイン板（当日ページの主役の枠・1画面に1つ）
画面で一番見てほしい1つ（TOP の「いま開催中」、マップで選んだ建物の情報）を、構内の案内板と同じ組み方で囲む。

```html
<section class="sign" aria-labelledby="…">
  <div class="sign__head"><h2 id="…">開催中</h2><span class="num">3件</span></div>
  <div class="sign__body">…リスト行…</div>
</section>
```

| 項目 | 値 |
|---|---|
| 見出しの帯 | 背景 `color-bg-sign`、文字 `color-text-on-fill`。見出しは display 書体 `font-xl`、件数は numeral 書体。内側 `space-3` `space-4` |
| 外枠 | 2px `color-border-sign`（帯と同じ青） |
| 中 | 背景 `color-bg-surface`、内側 `space-4` |
| 角丸 | `radius-block`（4px）。帯は上の角だけ枠に合わせる |
| 影 | なし |

- 中の行は `list-item.md` の行を並べ、行の間は 1px `color-border-default`。中の小見出しは罫線（2px `color-border-strong`）で区切り、2本目の帯を作らない
- 帯の上の場所コードの札は白地に青文字へ反転する（`place-code.md`）
- 1画面に2つ以上置かない（PROHIBITIONS 27）

## 2. 押せる1件（当日ページ）
写真が主役の企画・入口など、1件をそれだけで押させたいとき。

| 項目 | 値 |
|---|---|
| 背景 | `color-bg-surface` |
| 枠 | 1px `color-border-default` |
| 角丸 | `radius-block` |
| 影 | なし |
| 内側の余白 | `space-4` |

- 同じ大きさのカードを格子に並べて一覧を作らない。一覧はリスト行（`list-item.md`）を白い帯に並べる
- 写真がない件はカードにしない

## 3. 白い帯（カードの代わり）
一覧・表・お知らせを載せる白い面。カードと違い、角丸 `radius-block`・影なしで、本文の幅いっぱいに敷く。375px 未満では左右の余白をなくして画面幅いっぱいにしてよい。

## 4. 基本のカード（来場者企画）
| 項目 | 値 |
|---|---|
| 背景 | `color-bg-surface` |
| 角丸 | `radius-card`（14px） |
| 影 | `shadow-1` |
| 内側の余白 | `space-4`（大きいカードは上下 `space-5`・左右 `space-4`、または `space-6`） |
| 中の要素の間 | `space-2`〜`space-3` |

- カードの中にカードを入れない。中を区切るときは `color-bg-surface-soft` の面か、1px `color-border-default` の区切り線

## 5. カード型ボタン（来場者企画の画面の主役）
画面で一番してほしい操作を、図と大きいラベルを含むカード全体で押させる（来場者企画の「QRコードを読み取る」）。

| 項目 | 値 |
|---|---|
| 要素 | `<button>`（移動なら `<a>`）。中は図→説明→ラベルの縦並び、中央揃え、間 `space-3` |
| 角丸 / 影 | `radius-modal`（20px） / `shadow-2` |
| ラベル | カードの下部に primary ボタンと同じ見た目（`control-height-lg`、`font-lg`） |
| 押下 | `scale(var(--scale-press-card))`。hover は `translateY(-2px)` とラベルを押下色に |

- 1画面に1つ。ほかの操作は ghost ボタンか枠線のカードにして控えめにする

## 6. 場所カード（来場者企画で使っている例）
「ここは」タグ＋場所名の1行、区切り線の下に補足の1行。タグは `chip.md` のタグ（`color-bg-header` の塗り＋白文字＋アイコン14px）。場所名は `font-lg` `weight-bold`。当日ページでは場所コードの札（`place-code.md`）を使う。
