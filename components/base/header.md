# 共通ヘッダー

## 使う場面
全ページの最上部。ページの外枠として1つだけ置く。

## 構造
```html
<header class="site-header">
  <a class="site-header__logo" href="/2026/"><img src="（利用側が渡すロゴ）" width="755" height="228" alt="富大祭"></a>
  <div class="site-header__slot"><!-- ページ固有の要素（任意） --></div>
</header>
```

## 仕様
| 項目 | 値 |
|---|---|
| 高さ | `header-height`（67px）＋上セーフエリア（`padding-top: var(--safe-area-top)`） |
| 背景 / 文字 | `color-bg-header` / `color-text-on-fill` |
| 左右の余白 | `space-3`。広い画面では本文の幅にそろえる（背景は全幅） |
| ロゴ | 高さ `header-logo-height`（47px）、比率 755:228、`object-fit: contain` |
| 要素の間 | `space-3`、`justify-content: space-between` |
| 影 | なし |
| z-index | `chrome`（20） |

## ルール
- ロゴは通常の富大祭ロゴが標準。来場者企画だけ専用ロゴ（富大祭3190）に差し替える。画像は利用側が渡す（本リポジトリには置かない）
- 右側の領域にはページ固有の要素を1つだけ置く（来場者企画の進捗ドット、検索ボタンなど）。検索・日付・進捗の処理を共通ヘッダーに持ち込まない
- ページ名はヘッダーに書かず、本文の h1 に書く
- 右側に押せる要素を置くときは `touch-min` を守り、白い線アイコンにする
