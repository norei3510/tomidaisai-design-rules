# ボタン

使い分けは `guidelines/COMPONENT_GUIDE.md` §1.1。

## 種類
| 種類 | 背景 | 文字 | 枠 | 影 | 押下・hover |
|---|---|---|---|---|---|
| primary | `color-action-primary` | `color-text-on-fill` | なし | なし（来場者企画は `shadow-1`） | `color-action-primary-pressed` |
| secondary | `color-action-secondary` | `color-text-on-fill` | なし | なし（来場者企画は `shadow-1`） | `color-action-secondary-pressed` |
| ghost | `color-bg-surface` | `color-action-secondary` | 2px `color-action-secondary`（狭い所は1px） | なし | 背景 `color-bg-surface-soft` |

## 大きさ
| サイズ | 高さ | 左右の余白 | 文字 |
|---|---|---|---|
| 標準 | `control-height`（48px） | `space-6` | `font-body` `weight-bold` |
| 大（画面の主役） | `control-height-lg`（52px） | `space-6` | `font-lg` `weight-bold` |
| 小 | `touch-min`（44px）。見た目を小さくする場合も当たり判定は44px | `space-4` | `font-sm` `weight-bold` |

- 形は `radius-pill`。入力欄の隣に並べるボタンだけ `radius-input`
- 幅: 主要操作は幅いっぱい（`width: 100%`）。並べるときは2つまで、同じ幅（`grid-template-columns: 1fr 1fr`、間 `space-2`）
- アイコン付きはアイコン→文字、間 `space-2`、アイコンは文字と同じ色

## 状態
| 状態 | 表し方 |
|---|---|
| 押下 | `transform: scale(var(--scale-press))`、`duration-press` |
| hover | `@media (hover: hover)` の中で押下色へ。文字を薄くしない |
| フォーカス | `outline: 3px solid var(--color-focus-ring); outline-offset: 3px` |
| 読み込み中 | 文言を「送信中」などに変え、`disabled`＋`aria-busy="true"` |
| 無効 | `opacity: .45`、`cursor: default`。押せない理由を近くに書く |

## ルール
- primary は1画面に1つ
- ラベルは動詞で終え、1行に収める（`WRITING_GUIDE.md` §3）
- リンクとして移動するボタンは `<a>` で作り、`text-decoration: none` と色を指定する
