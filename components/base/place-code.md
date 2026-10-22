# 場所コードの札

建物・エリアを短いコード（例: `A`、`B2`）で示す札。会場の案内サインと同じ役割で、企画一覧・タイムテーブル・マップで同じコードを使う。【暫定】v0.3.0 で新設。コードの割り当ては実行委員会の会場図に合わせる（要確認）。

## 構造
```html
<span class="place-code">
  <span class="place-code__id">B2</span>
  <span class="place-code__name">共通教育棟</span>   <!-- 札だけで出すときは省略し、近くに建物名を書く -->
</span>
```

## 仕様
| 項目 | 値 |
|---|---|
| コードの面 | `color-action-secondary` の塗り＋`color-text-on-fill`（白文字 6.1:1） |
| コードの文字 | numeral 書体 `weight-bold`、`leading-tight`、字間 `tracking-numeral`。一覧の行では `font-sm`、見出しでは `font-xl` |
| コードの大きさ | 高さ `tag-height`（24px）以上、幅は高さ以上（1文字でも正方形）。見出しでは 40px 四方 |
| 角丸 | `radius-block`（4px） |
| 建物名 | 札の右に body 書体 `font-sm`（見出しでは display 書体 `font-xl`）。正式名称を略さない |
| サイン板の帯の上 | 反転: 面を `color-bg-surface`、文字を `color-text-link`（青）。建物名は `color-text-on-fill` |
| マップで選んだ場所 | 面を `color-status-now`（橙）に替え、2px `color-graphic-now` の外枠。色だけでなく枠の形でも分かるようにする |

## ルール
- 場所は文字より先に札で示す。同じページで、同じ場所に別の表し方（ピンのアイコン・色分け）を混ぜない
- コードは看板・地図の表記と同じにする（WRITING_GUIDE §2）
- 見出しに使うとき（企画一覧の建物ごとの区切り）は、札＋建物名＋件数を1行に並べ、その下に 2px `color-border-strong` の罫線
- 札だけを押せる要素にしない。押せるのは札を含む行全体
