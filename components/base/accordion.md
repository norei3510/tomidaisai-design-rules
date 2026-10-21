# アコーディオン

ヒント・注意事項・よくある質問など、全員は読まない補足を折りたたむ。

## 構造
`<details><summary>見出し</summary>本文</details>` を使う（JavaScript不要、キーボード操作可）。

## 仕様
| 項目 | 値 |
|---|---|
| 行 | 背景 `color-bg-surface`、`radius-chip`、行の間 `space-2` |
| 見出し | 最小高さ `control-height`（48px）、上下 `space-2`・左右 `space-4`、`font-body` `weight-bold` `color-text-link` |
| 開閉の印 | 右端の山形（8px、2px線）。閉＝下向き、開＝上向き。回転 `duration-base` `ease-standard` |
| 本文 | 背景 `color-bg-surface-soft`、上 `space-2`・左右 `space-3`・下 `space-4`、`font-sm` |
| フォーカス | 2px `color-action-secondary`、offset 2px |

- 既定のマーカー（▶）は消し、山形に統一する
- 1つの見出しに1つの話題。開いた状態を前提にした重要情報を入れない
