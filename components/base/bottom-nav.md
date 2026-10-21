# ボトムナビ

## 使う場面
全ページの最下部。サイトの5つの区分を移動する。

## 構造
```html
<nav class="bottom-nav" aria-label="サイト">
  <a class="bottom-nav__item" href="/2026/">
    <span class="bottom-nav__pill"><svg class="bottom-nav__icon" viewBox="0 0 24 24" aria-hidden="true">…</svg></span>
    <span class="bottom-nav__label">TOP</span>
  </a>
  <!-- 選択中の項目に aria-current="page" -->
</nav>
```

## 項目とリンク先
| 表示名 | リンク先 | 選択中にするページ |
|---|---|---|
| TOP | `/2026/` | TOP |
| ステージ | `/2026/stage/` | ステージと、互換のタイムテーブルURL |
| 企画 | `/2026/events/` | 企画一覧と企画詳細 |
| 来場者企画 | `/3190/` | 来場者企画の全画面 |
| マップ | `/2026/map/` | マップ |

- 並び順・表示名・数（5つ）を変えない。リンクはドメイン直下からのパス
- 来場者企画との行き来は通常のページ遷移。アプリの内部ルーターを共有しない

## 仕様
| 項目 | 値 |
|---|---|
| 高さ | `nav-height`（60px）＋下セーフエリア |
| 背景 | `color-bg-surface`、上辺 1px `color-border-default`、影 `shadow-nav` |
| 項目 | 5等分（`flex: 1 1 0`）、縦にアイコン→ラベル、間 `space-1` |
| アイコン | `icon-nav`（22px）、線幅 `icon-stroke`。選択中は `icon-stroke-active` |
| ピル | `nav-pill-width`×`nav-pill-height`（48×28）、`radius-pill`。選択中だけ `color-bg-surface-warm` |
| ラベル | `font-xs`、行間 1、折り返さない |
| 色 | 通常 `color-text-secondary`、選択中 `color-text-accent`＋`weight-bold` |
| 変化 | ピルの背景 `duration-base` `ease-standard` |

## アイコン（来場者企画の実装と同じ形）
| 項目 | path（viewBox 0 0 24 24、fill なし、stroke=currentColor、round） |
|---|---|
| TOP | `M4 10.5 12 4l8 6.5V19a1 1 0 0 1-1 1h-4.5v-5.5h-5V20H5a1 1 0 0 1-1-1z` |
| ステージ | `<rect x="9" y="3" width="6" height="11" rx="3"/>` ＋ `M5.5 11a6.5 6.5 0 0 0 13 0M12 17.5V21M8.5 21h7` |
| 企画 | `M5 21V4h11l-2 4 2 4H5` |
| 来場者企画 | `<circle cx="9" cy="8" r="3"/>` `M3.5 19a5.5 5.5 0 0 1 11 0` `<circle cx="17" cy="9" r="2.3"/>` `M15.8 14.1A4.5 4.5 0 0 1 21 18.5` |
| マップ | `M9 4 3.5 6v14L9 18l6 2 5.5-2V4L15 6 9 4zM9 4v14M15 6v14` |

## ルール
- 必ず `<a href>` を持つ `nav` にする。来場者企画の現行実装（`aria-hidden` の装飾タブ）は作り直し前の状態で、新しいページでは真似しない
- 選択中の項目に `aria-current="page"` を付ける
- 本文はナビの高さぶん下に余白を確保し、最後の要素がナビに隠れないようにする
- 広い画面でも下に置く（サイドバーやヘッダー内のタブに変えない）【暫定】
