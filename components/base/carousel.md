# カルーセル

チラシ・写真を1枚ずつ大きく見せ、横にスワイプして次へ進む。来場者企画の「近くの出展」で使っている形。

## 構造
```html
<ul class="carousel" aria-label="近くの出展">
  <li><button class="carousel__card"><img …><span>出展名</span></button></li>
</ul>
<div class="carousel__dots" aria-hidden="true"><span class="is-current"></span>…</div>
```

## 仕様
| 項目 | 値 |
|---|---|
| 1枚の幅 | 表示領域の72%まで、かつ高さに収まる大きさ（`min(72cqw, 100cqh * 画像の幅 / 高さ)`） |
| 並べ方 | 中央に1枚、両隣を少し見せる。`scroll-snap-type: x mandatory`、`scroll-snap-align: center`、間 `space-3` |
| 画像 | 比率を保つ（チラシは 848:1200）。1px `color-border-default`、角丸 6px【暫定】、`shadow-1` |
| 名前 | 画像の下、`font-sm`、1行で省略 |
| 位置の印 | 8px の丸、間 `space-2`。通常 `color-border-default`、いま見ている1枚 `color-action-secondary` |
| 押したとき | 拡大のダイアログ（`dialog.md`）で全体を表示 |
| 画像がないとき | `color-bg-surface-soft` の面＋ `icon-empty` のアイコン＋名前 |

## ルール
- スクロールバーは隠すが、キーボードでは左右に移動できる（各カードがフォーカス可能）
- 自動で送らない
- 高さが足りない画面ではカルーセルごと省くか、リスト行に切り替える
