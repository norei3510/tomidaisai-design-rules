# カード

## 1. 基本のカード
| 項目 | 値 |
|---|---|
| 背景 | `color-bg-surface` |
| 角丸 | `radius-card`（14px） |
| 影 | `shadow-1` |
| 内側の余白 | `space-4`（大きいカードは上下 `space-5`・左右 `space-4`、または `space-6`） |
| 中の要素の間 | `space-2`〜`space-3` |

- 水色の下地の上に置く。カードの中にカードを入れない。中を区切るときは `color-bg-surface-soft` の面か、1px `color-border-default` の区切り線
- 見出しは `font-lg` `weight-bold` `leading-heading`

## 2. 枠線のカード（補助）
影の代わりに 1px `color-border-default`。フォームなど、主役のカードより一段控えめにしたいときに使う。

## 3. カード型ボタン（画面の主役）
画面で一番してほしい操作を、図と大きいラベルを含むカード全体で押させる（来場者企画の「QRコードを読み取る」）。

| 項目 | 値 |
|---|---|
| 要素 | `<button>`（移動なら `<a>`）。中は図→説明→ラベルの縦並び、中央揃え、間 `space-3` |
| 角丸 / 影 | `radius-modal`（20px） / `shadow-2` |
| ラベル | カードの下部に primary ボタンと同じ見た目（`control-height-lg`、`font-lg`） |
| 押下 | `scale(var(--scale-press-card))`。hover は `translateY(-2px)` とラベルを押下色に |

- 1画面に1つ。ほかの操作は ghost ボタンか枠線のカードにして控えめにする

## 4. 場所カード（来場者企画で使っている例）
「ここは」タグ＋場所名の1行、区切り線の下に補足の1行。タグは `chip.md` のタグ（`color-bg-header` の塗り＋白文字＋アイコン14px）。場所名は `font-lg` `weight-bold`。
