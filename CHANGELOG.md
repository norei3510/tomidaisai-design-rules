# 更新履歴

## v0.3.0 — 2026-10-22

当日ページ（TOP・企画一覧・タイムテーブル・マップ）がAIっぽい定型の画面にならないよう、見た目の方向を「会場の案内サイン × 当日の紙パンフレット」に組み直した。色の値は変えていない。来場者企画と共通の既存トークンの名前・値も変えていない（追加のみ）。

- 値: 書体 `font-family.display`（りょうゴシック PlusN）・`numeral`（DIN 2014）・`numeral-narrow`（DIN 2014 Narrow）、サイズ `3xl`（32px）・`4xl`（40px）・`5xl`（56px）、行間 `display`、字間 `numeral`、角丸 `block`（4px）、色の用途 `bg-sign`・`border-sign`・`border-strong`・`status-now`・`graphic-now` を追加。影は追加しない（当日ページはダイアログ以外に影を使わない）。`tokens.css` に `--leading-tight` を追加（JSON にはあったがCSSに無かった）
- 判断: FOUNDATIONS に §1.2「AIっぽく見せない」、橙の意味を「いま・ここ・押す」に拡張（§2.1）、書体を3役割に分割（§3.1）、h1 を `3xl` に、1画面のサイズ上限を5段階に（§3.2）、カードの代わりに罫線と白い帯、主役は1画面1つの「サイン板」（青い見出しの帯＋青の外枠、§5）。旧デザインの名残（ずらし影・Acumin Pro Condensed）は引き継がない
- 禁則: PROHIBITIONS 9 を3書体に変更し、「AIっぽさ」24〜32 を追加
- 組み方: PAGE_LAYOUT_GUIDE §2 から英字アイブロウを外し、§6「当日ページ（1ページ1コンテンツ）」を追加。WRITING_GUIDE に場所コードの表記と、書かない文（どの祭りにも当てはまる文・使い方の説明）を追加
- 部品: `place-code.md`（場所コードの札）・`now-marker.md`（現在時刻の印）を新設。`card.md` を主役の枠・押せる1件・白い帯に再構成し、`list-item.md` の行の左端を時刻か場所コードに
- スマホ: タイムテーブルは 767px 以下で時刻順の行（1行44px 以上）に組み替え、格子は 768px 以上だけ。マップは地図を比率どおりに表示し、建物は場所コードの札で選び、拡大は全画面のダイアログ（PAGE_LAYOUT_GUIDE §6）
- 骨格: `top.html`・`timetable.html`・`map.html` を追加。`list.html` を場所コードごとの索引に、`detail.html` の基本情報を罫線＋白い帯に変更。`skeleton.css` に対応するスタイルを追加
- 確認: REVIEW_GUIDE に「AIっぽさ」の観点とチェックリストを追加
- 当日ページ用の Adobe Fonts キット `bqk8omc` を新設（中身はこの3書体だけ。来場者企画のキット `dlw1fic` とは分ける）。CSS 名と太さ（`ryo-gothic-plusn` 700・800、`din-2014` 400・700、`din-2014-narrow` 400・700）を確認済み。A-OTF ゴシックMB101 は Adobe Fonts に細字（300）しかないため見送った
- 【要確認】キットへの配信ドメインの登録、場所コードの割り当て

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
