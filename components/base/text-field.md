# 入力欄

## 構造
```html
<div class="field">
  <label for="code">場所コード</label>
  <p class="field__help" id="code-help">看板に書かれた英数字</p>
  <div class="field__row">
    <input id="code" aria-describedby="code-help code-error" …>
    <button class="button-inline">開く</button>   <!-- 任意 -->
  </div>
  <p class="field__error" id="code-error" role="alert" hidden>…</p>
</div>
```

## 仕様
| 項目 | 値 |
|---|---|
| ラベル | 常に表示。`font-sm` `weight-bold`。プレースホルダで代用しない |
| 補足 | ラベルの下、`font-sm` `leading-compact` `color-text-primary` |
| 入力欄 | 高さ `control-height`（48px）、左右 `space-3`、2px `color-border-input`、`radius-input`、背景 `color-bg-surface`、文字 `font-body`（コードは `font-lg`・字間 `code`） |
| 隣のボタン | 入力欄と同じ高さ、`radius-input`、ghost の配色、最小幅 72px、間 `space-2` |
| 囲み | 枠線のカード（`card.md` §2）、内側 `space-4`、要素の間 `space-2` |
| フォーカス | `outline: 3px solid var(--color-focus-ring); outline-offset: 3–4px` |
| エラー | 枠 `color-border-danger`＋`aria-invalid="true"`、欄の下に `color-text-danger` の文 |

## ルール
- 必須は「必須」と文字で示す
- 検証は入力欄を離れたときか送信時。1文字ごとに出さない
- エラー文は原因と直し方を書く（`WRITING_GUIDE.md` §4）
- キーボードが出たら入力欄と送信ボタンが見える位置へスクロールする
- `font-size` を16px未満にしない（iOSで拡大されるため）
