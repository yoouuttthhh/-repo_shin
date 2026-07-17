# CLAUDE.md
 
## レポジトリー: -repo_shin
- 目的: GitHubで管理できるナレッジを蓄積し、Claude CodeとWebフルスタック開発スキルを継続的に向上するため

## トーン
- 日本語 / Markdown / 簡潔で分かりやすく

## 条件
- 他のmdを参照するときにmd元を記載する
- 引用元情報を必ず記載する
- 不明点は作業前に必ず質問する
- 仮説や仮定を置く場合は「仮説」、「仮定」と明記する
- 過度に同調せず、客観的で率直な意見や対案を伝える

## 前提　(コンテキスト)
- **デザイン相談**は　`prj-reference/` を参照
- **その他**は　`knowledge/`を参照

## 禁止事項
- 「なぜ重要か」の理由がない提案はしない


## -repo_shin/ファイル構成

```
-repo_shin/
├─ README.md                      # リポジトリ全体の目的・地図
├─ CLAUDE.md                      # Claude用リポジトリ説明書
│
├─ checklist/                     # チェックリスト集
│  ├─ accessibility.md            # ウェブアクセシビリティのチェックリスト（WCAG 2.0）
│  └─ prompt.md                   # チェックリスト作成用プロンプト
│
├─ knowledge/                     # ツール・環境の使い方ナレッジ
│  ├─ github.md                   # GitHub運用ナレッジ
│  └─ dictionary.md               # コマンドリファレンス
│
├─ other/                         # Web開発（JS・PHP）の学習・検証用コード
│  ├─ js/                         # Node.js学習サンプル
│  │  ├─ double.js / file.js / hello.js / md.js
│  │  ├─ sample.html / sample.md / text.txt
│  │  ├─ package.json / package-lock.json
│  │  └─ node_modules/            # 依存パッケージ（marked）
│  └─ php/                        # PHP学習サンプル（現状は空）
│
├─ prj-reference/                 # 参考デザイン
│  ├─ CLAUDE.md                   # Claude用フォルダー説明書
│  ├─ reference-category.md       # 参考サイトの分類基準
│  ├─ UI-dictionary.md            # ユーザーインターフェースの分類基準
│  └─ web-accessibility.md        # ウェブアクセシビリティの基準（WCAG 2.0）
│
├─ prompt/                        # プロンプト置き場
│  ├─ asana_tem.md                # Asana用プロンプトテンプレート
│  └─ claude-tem.md               # Claude用プロンプトテンプレート
│
├─ seminars/                      # セミナー・勉強会の記録
│  ├─ CLAUDE.md                   # セミナー要約プロンプトテンプレート
│  ├─ 2026-07-10 ビームス&タカラトミーと考える 顧客の「行動」と「心理」が繋がる、ロイヤルティ設計.md
│  └─ 2026-07-13_クロードコード入門.md
│
└─ wiki/                          # 開発用語Wiki
   ├─ CLAUDE.md                   # wiki追加用プロンプトテンプレート
   └─ wiki.md                     # 開発用語集
```

- `checklist/` : チェックリスト集
- `knowledge/` : Claude CodeとWebフルスタック開発を手伝うナレッジ
- `other/` : Web開発の学習・検証用コード
- `prj-reference/` : デザイン知見
- `prompt/` : 再利用プロンプト置き場
- `seminars/` : セミナー・勉強会の記録
- `wiki/` : 開発用語集
