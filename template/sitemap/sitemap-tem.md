# sitemap-tem.md
サイトのURLからページ構成（サイトマップ）を取得し、
Markdown階層・CSV・XLSXの3形式で出力するためのプロンプトテンプレート。


## 精度を上げる方法（重要）

精度は入力方法によって大きく変わる。以下の順で精度が高い。

| 方法 | 精度 | 手順 |
|---|---|---|
| **①sitemap.htmlをコピペ** | ◎ 最高 | ブラウザで `サイトURL/sitemap.html` を開き全文コピー |
| **②sitemap.xmlをコピペ** | ◎ 最高 | ブラウザで `サイトURL/sitemap.xml` を開き全文コピー |
| **③ナビゲーションHTMLをコピペ** | ○ 高い | ブラウザの検証ツール（F12）でヘッダーのHTMLをコピー |
| **④URLのみ渡す** | △ 部分的 | Claudeが検索インデックスから推定。非公開ページは取れない |

**まず `サイトURL/sitemap.xml` または `サイトURL/sitemap.html` をブラウザで開いてみる。**
開けた場合はその内容をコピーして貼り付けると最も精度が高くなる。


## 使い方

1. 上記の方法でサイトマップデータを用意する
2. 下記プロンプトをClaudeに貼り付ける
3. 【入力データ】にURLまたはコピーしたデータを貼り付ける
4. 出力形式を指定して実行する


## プロンプト本文

```
以下のサイトのページ構成（サイトマップ）を取得・整理してください。

【サイト情報】
サイト名：[例：双日ケミカルトレーディング]
URL：[例：https://www.chemical-trading.sojitz.com/]

【出力形式】
以下から選んで指定してください（複数選択可）。
- Markdown階層形式
- CSV（sitemap.csv）
- XLSX（sitemap.xlsx）

【ルール】
- ページ名・URL・階層（1〜3階層）・備考（推定かどうか）を記載する
- 実際に確認できたページは「確認済み」、推定のページは「推定」と備考に明記する
- 404や非公開ページは含めない
- グローバルナビゲーションをベースに階層を整理する

【入力データ】
[以下のいずれかを貼り付ける]
・URLのみ：https://...
・sitemap.xmlの内容：（コピペ）
・sitemap.htmlの内容：（コピペ）
・ナビゲーションのHTML：（コピペ）
```


## 出力形式の例

### Markdown階層形式
```
サイト名/
├─ ホーム / https://example.com/
├─ 事業紹介 / https://example.com/business/
│  ├─ サービスA / https://example.com/business/service-a/
│  └─ サービスB / https://example.com/business/service-b/
├─ 会社概要 / https://example.com/company/
│  ├─ 会社概要 / https://example.com/company/profile/
│  └─ 沿革 / https://example.com/company/history/
└─ お問い合わせ / https://example.com/contact/
```

### CSV（sitemap.csv）
第1〜3階層を列で分けた構成。列はA〜L（12列）。

```
（空白行）
,,第1階層,,第2階層,,第3階層,,階層,,URL,メモ
（空白行）
,1,TOP,,,,,,/,,https://example.com/,
,,,1,会社について,,,,/company,,https://example.com/company,
,,,,,1,会社概要,,/company/about,,https://example.com/company/about,
（最終行）合計,,合計,,合計,ページ合計,総合計,,,
```

### XLSX（sitemap.xlsx）
- 列構成はCSVと同じ（A〜L・12列）
- ヘッダー行・データ行ともに背景色なし
- URLセルは青文字（`#0000FF`）
- 枠線なし
- 最終行に階層別ページ数の合計式（SUM関数）
- フォント：Arial統一
