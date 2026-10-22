# component-index — 部品の索引

> 答える問い: **どの部品があり、どれを読めばよいか。**
> 使い分けの判断は `guidelines/COMPONENT_GUIDE.md`。生成時はこの索引だけを読み、使う部品の仕様書だけを開く。

## base（どのページでも使う）

| 部品 | ファイル | 一言 |
|---|---|---|
| 共通ヘッダー | `base/header.md` | 青い帯。ロゴ左、ページ固有の要素右 |
| ボトムナビ | `base/bottom-nav.md` | 5項目のサイトナビ。選択中は橙＋ピル |
| ボタン | `base/button.md` | primary（橙）／secondary（青）／ghost（白＋青枠）。ピル形 |
| カード | `base/card.md` | 当日ページはサイン板（青い見出しの帯＋青の外枠、1画面1つ）・押せる1件・白い帯だけ。来場者企画のカードも含む |
| リスト行 | `base/list-item.md` | 文字中心の一覧の1行。左端に時刻か場所コード |
| 場所コードの札 | `base/place-code.md` | 建物を `A`・`B2` などの札で示す。一覧・表・地図で共通 |
| 現在時刻の印 | `base/now-marker.md` | 開催中の印・現在時刻の線・TOP の大きな時刻（橙） |
| チップ・タグ・バッジ | `base/chip.md` | 絞り込み・分類・ラベル |
| 入力欄 | `base/text-field.md` | ラベル＋入力＋補足／エラー |
| アコーディオン | `base/accordion.md` | `<details>` で補足を折りたたむ |
| ダイアログ | `base/dialog.md` | 確認・小窓・拡大表示 |
| 通知・トースト | `base/notice.md` | 画面上部の通知バーと、自動で消えるトースト |
| カルーセル | `base/carousel.md` | 画像を1枚ずつ横にめくる |

## specific（来場者企画だけ）

| 部品 | ファイル | 共通ページでの扱い |
|---|---|---|
| トミー君の吹き出し | `specific/guide-speech.md` | 条件付きで使える |
| 回答欄・進捗ドット・QR読み取り画面・問題枠 | `specific/README.md` | 使わない |
