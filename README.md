# 富大祭 共通デザインルール

富大祭のWebページで共有するデザインの判断・値・部品・骨格を、**答える問いごとに参照先を分けて**管理するpublicリポジトリです。版は v0.2.0。
基準は来場者企画（unifes26-vp `front/`）の 2026-10-21 時点の実装です。古い説明資料より、現行のCSSトークンを優先します。
構成は株式会社カナリーの [NestUI](https://github.com/SSK-TBD/NestUI) の参照設計を参考にしています。

## 索引 — 各ファイルが答える問い

| ファイル | 答える問い |
|---|---|
| `tokens/*.json` | この値は何か（色・文字・余白・寸法・角丸・影・動き）。**値の正** |
| `tokens/tokens.css` | CSSでどう書くか（JSONと同じ値の変数） |
| `guidelines/FOUNDATIONS.md` | 何を選ぶか、なぜそうするか |
| `guidelines/TOKEN_GUIDE.md` | トークンをどう参照するか |
| `guidelines/COMPONENT_GUIDE.md` | どの部品を使うか、状態をどう設計するか |
| `guidelines/PAGE_LAYOUT_GUIDE.md` | ページをどう組むか |
| `guidelines/WRITING_GUIDE.md` | 画面の文をどう書くか |
| `guidelines/PROHIBITIONS.md` | 何をしてはいけないか |
| `components/component-index.md` | どの部品があるか（各仕様書への索引） |
| `layout_patterns/layout-index.md` | どの骨格から組み始めるか |
| `review/REVIEW_GUIDE.md` | できた画面をどう確かめるか |
| `review/FINDINGS.md` | レビューの気づきをどこへ戻すか |
| `pages/` | このページだけで、なぜこう決めたか |
| `DESIGN.md` | OpenDesign などに1枚で渡すときの入口 |

## 場面ごとに読むもの

| 場面 | 毎回読む | 必要なときだけ読む |
|---|---|---|
| 新しいページを作る | FOUNDATIONS・PROHIBITIONS・PAGE_LAYOUT_GUIDE・WRITING_GUIDE・layout-index | component-index → 使う部品の仕様書、COMPONENT_GUIDE（部品の選択に迷ったとき） |
| 既存ページを直す | そのページの `pages/*.md`・PROHIBITIONS | 直す部品の仕様書 |
| レビュー: 部品 | FOUNDATIONS・PROHIBITIONS・COMPONENT_GUIDE・TOKEN_GUIDE | 使った部品の仕様書 |
| レビュー: レイアウト | PAGE_LAYOUT_GUIDE・layout-index | 使った骨格のHTML |
| レビュー: 文言 | WRITING_GUIDE | — |
| 値を変える | TOKEN_GUIDE | 関係する `tokens/*.json` |

作るとき（発散）は原則と骨格を土台に部品を選びながら組み、確かめるとき（収束）は観点ごとに読むものを絞ります。

## ディレクトリ

```
tomidaisai-design-rules/
├── README.md              索引（このファイル）
├── AGENTS.md              AIエージェント向けの作業ルール
├── DESIGN.md              1枚版の入口（OpenDesign 用）
├── CHANGELOG.md           更新履歴
├── tokens/                値の正（DTCG形式のJSON）とCSS版
├── guidelines/            判断のルール 6本
├── components/
│   ├── component-index.md
│   ├── base/              どのページでも使う部品 11種
│   └── specific/          来場者企画だけの部品
├── layout_patterns/       骨格HTML 4種と skeleton.css、選び方
├── review/                レビュー観点と、気づきの記録
└── pages/                 ページごとの判断（ひな形あり）
```

## 骨格を見る
`layout_patterns/list.html` などをブラウザで直接開きます（`tokens/tokens.css` と `skeleton.css` を相対パスで読みます）。

## 取り込みと更新
- 利用側はタグ（例: `v0.2.0`）を固定して `tokens/tokens.css` を取り込みます。実行時にGitHubから取得する必要はありません
- 値を変えるときは JSON → `tokens.css` → `CHANGELOG.md` の順に直します。各サイトへの適用はサイトごとに確認します
- 共通ルールの追加・変更は `review/FINDINGS.md` に提案し、人が承認してから反映します
- 分類: 【確定】実装と根拠の両方で確認できる／【暫定】実装にあるが根拠が未確認、または本リポジトリで新設／【未定】決められない

## 管理しないもの
謎解きの問題・答え・物語・進捗処理、画像（ロゴ・トミー君・チラシ）、企画データ、元のExcel、フォント本体、認証情報。

## 適用状況
- 来場者企画: 本ルールの基準元。primitive 変数は `front/src/design-tokens.css` と同じ名前・値です
- 当日サイト: 未適用。ヘッダーとボトムナビの部品実装は後続の作業です
