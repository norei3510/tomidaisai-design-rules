# 現在時刻の印

「いま」を示す橙の印。当日ページの橙の主な使い道（`guidelines/FOUNDATIONS.md` §2.1）。【暫定】v0.3.0 で新設。

## 1. 開催中の印（一覧・TOP）
| 項目 | 値 |
|---|---|
| 面 | `color-status-now`（橙の濃色）＋`color-text-on-fill` |
| 文字 | 「開催中」。body 書体 `font-xs` `weight-bold`、`leading-tight` |
| 形 | 高さ `tag-height`、角丸 `radius-pill`。文字の左に直径8pxの白い丸 |

- 色だけでなく「開催中」の文字で伝える
- 終わった件には印を付けない。始まる前の件は時刻だけを出す

## 2. 現在時刻の線（タイムテーブル）
| 項目 | 値 |
|---|---|
| 線 | 2px `color-graphic-now`、表の幅いっぱい |
| ラベル | 線の左端に時刻（例: 「13:42」）。`color-status-now` の面＋白文字、numeral 書体 `font-sm` `weight-bold`、角丸 `radius-block` |
| 位置 | 表の時刻の目盛りから計算する（開始時刻からの分数 × 1分あたりの高さ） |
| 更新 | ページを開いたときと1分ごと |
| 767px 以下（行の一覧） | 線を表に重ねず、いま始まっている演目の行と次の演目の行の間に、区切りの行として入れる（2px `color-graphic-now` の線＋同じラベル）。いま始まっている演目の行には §1 の「開催中」の印 |

- 線とラベルの組で使う（線だけにしない）。読み上げ用に `aria-label="現在時刻 13時42分"` をラベルに付ける
- 開催日以外・開催時間外は出さない

## 3. 主役の現在時刻（TOP）
| 項目 | 値 |
|---|---|
| 数字 | numeral 書体 `font-5xl` `weight-bold`、`leading-display`、`tabular-nums`。色は `color-text-primary` |
| 印 | 数字の左上に「いま」の札（§1 と同じ形） |

- 時刻は `<time datetime="…">` で書く
- 繰り返しの点滅・秒の表示はしない（FOUNDATIONS §7）
