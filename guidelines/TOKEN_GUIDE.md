# TOKEN_GUIDE — トークンをどう参照するか

> 答える問い: **CSSでどの変数を書けばよいか。新しい値が必要なときはどうするか。**

## 1. 3層の参照ルート

```
primitive（素の値）      semantic（用途）              component（部品内だけの別名）
--main-dark: #18679d  →  --color-action-secondary  →  --button-secondary-bg（部品のCSS内で定義）
```

| 層 | 例 | 誰が使うか |
|---|---|---|
| primitive | `--main-dark` `--space-4` `--radius-card` | semantic 層の定義と、余白・角丸・文字サイズの直接指定 |
| semantic | `--color-text-primary` `--color-action-primary` | **新しいページの色はここから選ぶ** |
| component | `--button-bg` など | 1つの部品の中で状態を切り替えるときだけ。部品のCSS内で semantic を参照して定義する |

- **色は semantic を使う**。`--accent-text` と書かず `--color-action-primary`（主要ボタン）か `--color-text-accent`（橙の文字）と書く。同じ値でも用途が違えば別の名前を使う
- 余白・角丸・文字サイズ・影は primitive を直接使ってよい（`--space-4`、`--radius-card`、`--font-body`）
- `--radius` と `--shadow` は来場者企画との互換名。新しいCSSでは使わない

## 2. 正本と同期

| 何を | どこが正か |
|---|---|
| 値 | `tokens/*.json` |
| CSS変数 | `tokens/tokens.css`（JSONと同じ値を手で揃える） |
| 来場者企画での実装 | unifes26-vp `front/src/design-tokens.css`（本リポジトリの primitive と同じ名前・値） |

- 値を変えるときは JSON → `tokens.css` → `CHANGELOG.md` の順に直す。各サイトへの反映はサイトごとに確認する
- 部品の仕様書（`components/`）に数値を併記していても、食い違ったらトークンが正

## 3. 書いてはいけない値

- 16進カラーや `rgb()` の直書き（画像・イラスト・問題素材の中の色は例外）
- トークンにない余白（例: `10px`、`14px`）。必要なら近いトークンに寄せる
- 13px・15px などトークンにない文字サイズ

## 4. 新しいトークンが必要なとき

1. 既存の semantic で表せないかを確認する（同じ意味なら既存を使う）
2. 1ページだけで使う値なら、トークンにせずそのページの判断として `pages/<ページ名>.md` に残す
3. 2ページ以上で使う見込みがあるときだけ、`review/FINDINGS.md` に提案として記録し、人が承認してから JSON と `tokens.css` に追加する
4. 追加するトークンには `$description` に用途を書く

## 5. OpenDesign・外部ツールでの使い方

- 生成したHTMLの `<head>` で `tokens/tokens.css` を読むか、`:root` の中身をそのまま `<style>` の先頭に貼る
- 部品のCSSは semantic 変数だけで書き、`:root` に置く（モーダル・トーストも同じ変数を継承できるように）
