# 通知バー・トースト

## 通知バー
画面全体に関わる注意（保存できない・通信できない・場所が違う）。ヘッダーの直下、本文の上に置く。

| 項目 | 値 |
|---|---|
| 面 | 背景 `color-bg-surface`、下辺 2px `color-graphic-accent` |
| 内側 | 上下 `space-3`・左右 `space-4`、要素の間 `space-2` |
| 文 | `font-xs`〜`font-sm`、`leading-compact`〜1.6 |
| 閉じる | 右端、「×」に `aria-label="案内を閉じる"`、40px以上（推奨 `touch-min`） |
| 役割 | 急ぎは `role="alert"`、それ以外は `role="status"` |

- 通知バーは同時に1つ。新しい通知が来たら置き換える

## トースト【暫定】
操作の結果（コピーした・保存した）を短く伝える。

| 項目 | 値 |
|---|---|
| 位置 | ボトムナビの上 `space-4`、中央 |
| 面 | 背景 `color-text-primary`、文字 `color-bg-surface` `font-sm` `weight-bold`、`radius-pill`、上下 `space-2`・左右 `space-4` |
| 幅 | 本文の幅 − `space-6` まで |
| 表示時間 | 約2秒、`role="status"` |
| 動き | 出現 `duration-enter` / 消去 `duration-exit`（不透明度と移動だけ） |

- 失敗はトーストにせず、操作の近くにエラー文を出す
