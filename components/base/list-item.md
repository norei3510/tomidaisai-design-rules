# リスト行

文字が中心の一覧（企画・ステージの演目・場所）の1行。【暫定】来場者企画には無い部品で、共通部品として新設。

## 構造
```html
<ul class="list" role="list">
  <li><a class="list-item" href="…">
    <img class="list-item__thumb" …>              <!-- 任意 -->
    <span class="list-item__body">
      <span class="list-item__title">企画名</span>  <!-- 各行は block -->
      <span class="list-item__meta">場所・時間</span>
    </span>
    <svg class="list-item__chevron" …></svg>
  </a></li>
</ul>
```

## 仕様
| 項目 | 値 |
|---|---|
| 一覧の面 | カード1枚（`card.md` §1）の中に行を並べ、行の間は1px `color-border-default` |
| 行の高さ | 最小 `touch-min`＋上下 `space-3` |
| 左右の余白 | `space-4` |
| サムネイル | 48〜64px 四方。チラシ・写真は比率を保つ（切り抜くなら一覧のサムネイルだけ、`object-fit: cover` を明示） |
| 名前 | `font-body` `weight-bold`、1行で省略（データの文字なので可） |
| 補足 | `font-sm` `color-text-secondary`、1行 |
| 右端 | 移動するなら右向きの線アイコン（`color-text-link`）。時刻などの値なら `white-space: nowrap` |
| 押下・hover | 背景 `color-bg-surface-soft` |

## ルール
- 名前と補足は別々のブロック要素にする（同じ行の span に詰めない）
- 省略した名前は詳細ページで全文を出す
- 件数が50を超えるときは、絞り込み（チップ）か分割を用意する
