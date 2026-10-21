# チップ・タグ・バッジ

| 種類 | 用途 | 押せるか |
|---|---|---|
| フィルターチップ | 一覧の絞り込み | 押せる |
| タグ | 分類・場所などのラベル | 押せない |
| バッジ | 数・状態の印（「第1問」など） | 押せない |

## フィルターチップ【暫定】
| 項目 | 値 |
|---|---|
| 高さ | `touch-min`（44px）。見た目の高さを抑える場合も当たり判定は44px |
| 左右 | `space-4` |
| 角丸 | `radius-pill` |
| 通常 | 背景 `color-bg-surface`、1px `color-border-default`、文字 `color-text-primary` `font-sm` |
| 選択中 | 背景 `color-action-secondary`、文字 `color-text-on-fill` `weight-bold`、`aria-pressed="true"` |
| 並べ方 | 横スクロール1行（次のチップが端から少し見える）、間 `space-2` |

- ラベルは4文字まで。長いものはチップにせずリストにする

## タグ
| 項目 | 値 |
|---|---|
| 高さ | `tag-height`（24px） |
| 左右 | `space-2` |
| 角丸 | `radius-chip` |
| 色 | 背景 `color-bg-header`、文字 `color-text-on-fill` `font-xs` `weight-bold`、行間 1 |
| アイコン | 任意、`icon-inline`（14px）、文字との間 2px |

## バッジ
| 項目 | 値 |
|---|---|
| 形 | `radius-pill`、上下 `space-1`・左右 `space-3` |
| 色 | 背景 `color-action-primary`、文字 `color-text-on-fill` `font-xs` `weight-bold` |

- バッジは1画面に1種類。カードの見出しの前に置く
