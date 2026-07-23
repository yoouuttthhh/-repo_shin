# -repo_shin
デザイナーとしての学習記録・成長の軌跡を残すリポジトリ。
「企画→Webサイト開発→立ち上げ」までの一連を学ぶ過程を記録し、継続的にアップデートしていく。


## 概要
GitHubで管理できるナレッジを蓄積し、
Claude CodeとWebフルスタック開発スキルを継続的に向上するため。


## ファイル構成
```
-repo_shin/
├─ README.md                      # リポジトリ全体の目的・地図
├─ CLAUDE.md                      # Claude用リポジトリ説明書
│
├─ Checklist/                     # チェックリスト集
│  ├─ accessibility.md            # ウェブアクセシビリティのチェックリスト（WCAG 2.0）
│  └─ prompt.md                   # チェックリスト作成用プロンプト
│
├─ Knowledge/                     # ツール・環境の使い方ナレッジ
│  ├─ github.md                   # GitHub運用ナレッジ
│  └─ command-dictionary.md       # コマンドリファレンス
│
├─ Other/                         # Web開発（JS・PHP）の学習・検証用コード
│  ├─ js/                         # Node.js学習サンプル
│  │  ├─ double.js / file.js / hello.js / md.js
│  │  ├─ sample.html / sample.md / text.txt
│  │  ├─ package.json / package-lock.json / package.json.bak
│  │  └─ node_modules/            # 依存パッケージ（marked）
│  └─ php/                        # PHP学習サンプル（現状は空）
│
├─ -prj-reference/                # 参考デザイン
│  ├─ CLAUDE.md                   # Claude用フォルダー説明書
│  ├─ reference-category.md       # 参考サイトの分類基準
│  ├─ UI-dictionary.md            # ユーザーインターフェースの分類基準
│  └─ web-accessibility.md        # ウェブアクセシビリティの基準（WCAG 2.0）
│
├─ Seminars/                      # セミナー・勉強会の記録
│  ├─ CLAUDE.md                   # セミナー要約プロンプトテンプレート
│  ├─ 2026-07-10 ビームス&タカラトミーと考える 顧客の「行動」と「心理」が繋がる、ロイヤルティ設計.md
│  └─ 2026-07-13_クロードコード入門.md
│
├─ Template/                      # プロンプト・テンプレート置き場
│  ├─ CLAUDE.md                   # Claude用フォルダー説明書
│  ├─ template-style.md           # Markdown記述スタイルルール
│  ├─ claude-tem.md               # Claude用プロンプトテンプレート（CLAUDE.md作成用）
│  ├─ readme-tem.md               # README用プロンプトテンプレート
│  ├─ CHANGELOG-tem.md            # CHANGELOG用プロンプトテンプレート
│  ├─ asana-tem.md                # Asana用プロンプトテンプレート
│  ├─ meeting-notes-tem.md        # 議事録作成用プロンプトテンプレート
│  ├─ faq-tem.md                  # FAQ追記用プロンプトテンプレート
│  ├─ Competitor/                 # 競合分析テンプレート置き場
│  │  ├─ competitor-tem.md        # 競合ポジショニングマップ作成用テンプレート
│  │  └─ thumbs/                  # サムネ画像置き場（現状は空）
│  └─ Sitemap/                    # サイトマップテンプレート置き場
│     ├─ sitemap-tem.md           # サイトマップ作成用プロンプトテンプレート
│     ├─ sitemap-sample.csv       # サイトマップCSVのサンプル
│     └─ sitema-sample.xlsx       # サイトマップXLSXのサンプル
│
└─ Wiki/                          # 開発用語Wiki
   ├─ CLAUDE.md                   # wiki追加用プロンプトテンプレート
   └─ wiki.md                     # 開発用語集
```


## 使い方・運用ルール
- セミナー参加後はその日のうちに `seminars/yyyy-mm-dd_セミナー名.md` を作成する
- 新しい用語を学んだら `wiki/wiki.md` に追記する
- ファイル構成が変わったらこのREADME.mdと `CLAUDE.md` を更新する


## 関連リンク
- [CLAUDE.md](./CLAUDE.md)
