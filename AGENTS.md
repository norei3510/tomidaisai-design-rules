# 作業ルール

## このリポジトリを編集するとき
- subagentを作成・起動せず、メインエージェントが直接作業する。
- 回答は結論または次の行動から始める。複数手順は番号付き、原則5項目以内。
- このリポジトリの作業で、既存のevent・unifes26-vpリポジトリを変更しない。
- このリポジトリはpublic。共通仕様・トークン・骨格のみを置く。企画データ・原稿・Excel・画像・ゲーム内容・認証情報は追加しない。
- 古い説明資料より現行実装の値を優先する。来場者企画だけの制約を共通要件にしない。
- 1つの情報は1か所にだけ正を置く（`README.md` の索引）。値は `tokens/*.json`、判断は `guidelines/`、部品は `components/`、骨格は `layout_patterns/`、ページ固有は `pages/`。
- 値を変えたら JSON・`tokens/tokens.css`・`CHANGELOG.md` を同時に直す。

## このルールでUIを作るとき（生成）
1. 毎回読む: `guidelines/FOUNDATIONS.md`・`PROHIBITIONS.md`・`PAGE_LAYOUT_GUIDE.md`・`WRITING_GUIDE.md`・`layout_patterns/layout-index.md`
2. 骨格を1つ選び、`components/component-index.md` から使う部品の仕様書だけを開く
3. 色は `tokens/tokens.css` の semantic 変数（`--color-*`）、余白・角丸・文字サイズは primitive 変数で書く
4. 共通ルールにない判断をしたら、`pages/_template.md` を写して理由を残す
5. 内容が未確定の場所は `［ ］` のプレースホルダにする。数字・企画情報を作らない

## このルールでUIを確かめるとき（レビュー）
- `review/REVIEW_GUIDE.md` の観点ごとに、表にあるファイルだけを読む
- 共通ルールに関わる気づきは `review/FINDINGS.md` に「提案」として記録し、共通ルールを直接書き換えない
