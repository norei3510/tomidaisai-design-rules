# DESIGN.md — 富大祭 共通デザイン（1枚版の入口）

> 正: 各行の「参照先」。本ファイルは選択の要約と参照先だけを記録する（ルールの詳細は再掲しない）。
> 本ファイルに無い項目は参照先に従う。`（要確認）` は生成前に人が確定する。
> OpenDesign などで新しいページを作るときは、本ファイルと `tokens/tokens.css` を渡し、必要に応じて参照先を読ませる。

## 方向性
- 会場を歩きながら片手のスマートフォンで見る、富大祭の公式ページ
- 「**会場の案内サイン × 当日の紙パンフレット**」。白いカードを並べず、紺の罫線と大きな見出し・数字で組む
- 水色の下地（約60%）・白い帯（約25%）・青のヘッダーと副操作・**橙は「いま・ここ・押す」だけ**
- 1ページ1コンテンツ。コンテンツそのものを最初の画面に出し、前置きをしない。AIっぽい定型を避ける → `guidelines/FOUNDATIONS.md` §1–2、`PROHIBITIONS.md`「AIっぽさ」

## 要約と参照先

| 項目 | 選択 | 参照先 |
|---|---|---|
| 色 | 下地 `--color-bg-page`、面 `--color-bg-surface`、本文 `--color-text-primary`、罫線 `--color-border-strong`、いま `--color-status-now`・`--color-graphic-now`、主要操作 `--color-action-primary`（1画面1つ）、副操作 `--color-action-secondary` | `tokens/color.json`・FOUNDATIONS §2 |
| 書体 | 見出し `--font-family-display`（りょうゴシック PlusN 700・800）・数字 `--font-family-numeral`（DIN 2014。表は `--font-family-numeral-narrow` の DIN 2014 Narrow）・本文 `--font-family-body`（Noto Sans JP）。h1 32px、主役の数字 56px、本文16px、最小12px | `tokens/typography.json`・FOUNDATIONS §3 |
| 余白 | 4の倍数。画面左右16px、帯の内側16px、セクション間24〜32px | `tokens/spacing.json`・FOUNDATIONS §4 |
| 形 | 罫線（紺2px）と白い帯（角丸4px・影なし）。主役はサイン板1つ（青い見出しの帯＋青2pxの外枠）。影はダイアログだけ。ボタン・チップはピル | `tokens/radius.json`・`elevation.json`・FOUNDATIONS §5 |
| 骨格 | 共通ヘッダー（青・67px）→ 本文（縦スクロール、幅480px まで）→ ボトムナビ（白・60px・5項目）。当日ページは TOP・一覧・タイムテーブル・マップの骨格から | PAGE_LAYOUT_GUIDE §1・§6・`layout_patterns/` |
| 部品 | 場所コードの札・現在時刻の印・リスト行・カード（主役の枠）・ボタン・チップ・入力・アコーディオン・ダイアログ・通知・カルーセル | `components/component-index.md` |
| 状態 | 読み込み中・空・エラー・完了・無効を必ず用意 | COMPONENT_GUIDE §2 |
| 文 | です・ます、「、。」、ボタンは動詞で終える | `guidelines/WRITING_GUIDE.md` |
| 禁則 | 橙（#F26A00）に白文字、水色に補足色、12px未満、44px未満の操作、直書きの色、カードの羅列・英字アイブロウ・前置きの文などAIっぽい定型 ほか | `guidelines/PROHIBITIONS.md` |
| 確認 | 観点別チェックリスト | `review/REVIEW_GUIDE.md` |

## ページごとの記入欄（生成前に埋める）
- ページ名とURL: （要確認）
- 目的と主な操作: （要確認）
- 骨格: top / list / timetable / map / detail / action / message のどれか → `layout_patterns/layout-index.md`
- 使う場所コードと建物名の対応: （要確認。実行委員会の会場図に合わせる）
- ボトムナビで選択中にする項目: TOP / ステージ / 企画 / 来場者企画 / マップ（要確認）
- 表示する実データ（企画名・時間・場所・画像）: （要確認。未確定ならプレースホルダ）
