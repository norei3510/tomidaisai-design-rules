# ダイアログ

`<dialog>` 要素と `showModal()` で作る（フォーカスの閉じ込め・Escで閉じるが標準で付く）。

## 種類
| 種類 | 用途 | 幅 |
|---|---|---|
| 確認 | 消す・やり直すなど取り消せない操作の前 | `min(100% - 32px, 360px)` |
| 小窓 | ヒント・補足・説明 | `min(100% - 32px, 390px)` |
| 拡大 | チラシ・画像を大きく見る | `min(100% - 32px, 420px)`、高さ `92dvh` まで |

## 仕様
| 項目 | 値 |
|---|---|
| 背面 | `::backdrop` に `color-bg-overlay` |
| 面 | 背景 `color-bg-surface`（小窓は `color-bg-page` も可）、`radius-card`（確認は `radius-modal`）、`shadow-2` |
| 内側 | `space-4`（確認は上下 `space-6`・左右 `space-5`） |
| 見出し | `font-body`〜`font-lg` `weight-bold`、右上に閉じるボタン |
| 閉じるボタン | 「閉じる」の文字付き、最小 `touch-min`、ghost の配色（1px枠・`radius-chip`） |
| 確認のボタン | 横に2つ、同じ幅。取り消せない操作は primary、やめるは ghost |
| 出現 / 消去 | `duration-enter` `ease-standard` / `duration-exit` `ease-exit`（不透明度と移動だけ） |

## ルール
- 閉じる方法を必ず見える形で置く（背面のタップだけにしない）
- 主な流れ（申し込み手順など）をダイアログに入れない
- 閉じたら、開いたボタンにフォーカスを戻す
- 画像の拡大は比率を保って全体を表示する（`max-width: 100%`、`height: auto`）
