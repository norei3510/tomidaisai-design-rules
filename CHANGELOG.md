# 更新履歴

## v0.2.0 — 2026-10-21

NestUI の参照設計にならい、答える問いごとに参照先を分ける構成へ作り直した。

- 値: `tokens/` に色・文字・余白・寸法・角丸・影・動きの JSON（DTCG形式）を追加し、値の正とした。`tokens.css` に semantic 層（`--color-*`）、寸法、動き、`--danger-text`、`--shadow-nav` を追加。primitive の変数名・値は v0.1.0 と同じ
- 判断: `rules/foundations.md` を `guidelines/` の6本（FOUNDATIONS・TOKEN_GUIDE・COMPONENT_GUIDE・PAGE_LAYOUT_GUIDE・WRITING_GUIDE・PROHIBITIONS）に分割・拡充
- 部品: `rules/shared-shell.md` を `components/base/header.md`・`bottom-nav.md` に移し、ボタン・カードなど9部品の仕様と、来場者企画だけの部品の扱い（`components/specific/`）を追加
- 骨格: `layout_patterns/` に一覧・詳細・操作・結果の4骨格HTMLと選び方を追加
- 運用: `review/`（観点別チェックと気づきの記録）、`pages/`（ページごとの判断のひな形）、1枚版の入口 `DESIGN.md` を追加
- 削除: `rules/`（内容は上記へ移動）
- unifes26-vp `front/` の旧デザイン資料（DESIGN.md・TOKENS.md・COMPONENTS.md・INVENTORY.md）を本リポジトリへ統合したため、元のファイルを削除

## v0.1.0 — 2026-10-21

現行来場者企画から共有可能な色・文字・余白・角丸・影を抽出。共通ヘッダー、5項目のナビ、セーフエリア、操作状態を文書化。ゲーム固有の値と内容は共通仕様から除外。今回の当日サイト移植への適用は行わない。
