# DESIGN.md — 富大祭 共通デザイン（1枚版の入口）

> 正: 各行の「参照先」。本ファイルは選択の要約と参照先だけを記録する（ルールの詳細は再掲しない）。
> 本ファイルに無い項目は参照先に従う。`（要確認）` は生成前に人が確定する。
> OpenDesign などで新しいページを作るときは、本ファイルと `tokens/tokens.css` を渡し、必要に応じて参照先を読ませる。

## 方向性
- 会場を歩きながら片手のスマートフォンで見る、富大祭の公式ページ
- 水色の下地（約60%）・白いカード（約25%）・青のヘッダーと副操作・**橙は押してほしい場所だけ**
- 明るく、読みやすく、迷わない。装飾は最後 → `guidelines/FOUNDATIONS.md` §1–2

## 要約と参照先

| 項目 | 選択 | 参照先 |
|---|---|---|
| 色 | 下地 `--color-bg-page`、面 `--color-bg-surface`、本文 `--color-text-primary`、主要操作 `--color-action-primary`（1画面1つ）、副操作 `--color-action-secondary` | `tokens/color.json`・FOUNDATIONS §2 |
| 書体 | Noto Sans JP のみ。本文16px・行間1.7、見出し22/18px・行間1.3、最小12px | `tokens/typography.json`・FOUNDATIONS §3 |
| 余白 | 4の倍数。画面左右16px、カード内16px、セクション間24〜32px | `tokens/spacing.json`・FOUNDATIONS §4 |
| 形 | ボタンはピル、カード14px、入力10px、タグ8px、モーダル20px。影は2段階 | `tokens/radius.json`・`elevation.json` |
| 骨格 | 共通ヘッダー（青・67px）→ 本文（縦スクロール、幅480px まで）→ ボトムナビ（白・60px・5項目） | PAGE_LAYOUT_GUIDE §1・`layout_patterns/` |
| 部品 | ボタン・カード・リスト行・チップ・入力・アコーディオン・ダイアログ・通知・カルーセル | `components/component-index.md` |
| 状態 | 読み込み中・空・エラー・完了・無効を必ず用意 | COMPONENT_GUIDE §2 |
| 文 | です・ます、「、。」、ボタンは動詞で終える | `guidelines/WRITING_GUIDE.md` |
| 禁則 | 橙（#F26A00）に白文字、水色に補足色、12px未満、44px未満の操作、直書きの色 ほか | `guidelines/PROHIBITIONS.md` |
| 確認 | 観点別チェックリスト | `review/REVIEW_GUIDE.md` |

## ページごとの記入欄（生成前に埋める）
- ページ名とURL: （要確認）
- 目的と主な操作: （要確認）
- 骨格: list / detail / action / message のどれか → `layout_patterns/layout-index.md`
- ボトムナビで選択中にする項目: TOP / ステージ / 企画 / 来場者企画 / マップ（要確認）
- 表示する実データ（企画名・時間・場所・画像）: （要確認。未確定ならプレースホルダ）
