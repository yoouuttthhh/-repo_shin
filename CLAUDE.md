# CLAUDE.md
 
## レポジトリー: -repo_shin
- 目的: GitHubで管理できるナレッジを蓄積し、Claude CodeとWebフルスタック開発スキルを継続的に向上するため

## 出力
- 日本語 / Markdown / 簡潔で分かりやすく

## -repo_shinの/ファイル構成

```
-repo_shin/
├─ README.md                      # リポジトリ全体の目的・地図
├─ CLAUDE.md                      # Claude用リポジトリ説明書
│
├─ checklist/                     # チェックリスト集
│  └─ accessibility-checklist.md  # ウェブアクセシビリティのチェックリスト（WCAG 2.0）
│
├─ development/                   # Web開発（JS・PHP）の学習・検証用コード
│  ├─ js/                         # Node.js学習サンプル
│  └─ php/                        # PHP学習サンプル
│
└─ knowledge/                     # ツール・環境の使い方ナレッジ
   ├─ github-knowledge.md
   ├─ command.md                  # コマンド一覧
   │
   ├─ seminars/                   # セミナー・勉強会の記録
   │  ├─ seminar-template.md
   │  └─ yyyy-mm-dd_xxxxxx.md
   │
   ├─ wiki/                       # 開発用語Wiki
   │  ├─ wiki-template.md         # wiki追加用プロンプトテンプレート
   │  └─ wiki.md                  # 開発用語集
   │
   └─ reference/                  # 参考デザイン
      ├─ README.md                # このフォルダーの目的・地図
      ├─ reference-category.md    # 参考サイトの分類基準
      ├─ UI-dictionary.md         # ユーザーインターフェースの分類基準
      ├─ web-accessibility.md     # ウェブアクセシビリティの基準（WCAG 2.0）
      │
      ├─ case-study/              # 参考サイトの事例研究md（現状は空）
      ├─ src/                     # reference/の画像などのアセット（現状は空）
      └─ development/             # reference/を表示するサイト実装（現状は空）
```

- `checklist/` : チェックリスト集
- `development/` : Web開発の学習・検証用コード（`reference/development/` とは別物）
- `knowledge/` : Claude CodeとWebフルスタック開発を手伝うナレッジ
- `reference/` : デザイン知見

## 振る舞い
- 他のmdを参照するときにmd元を記載する
- 引用元情報を必ず記載する
- 不明点は作業前に必ず質問する。「なぜ重要か」の理由がない提案はしない
- 仮説や仮定を置く場合は「仮説」、「仮定」と明記する
- 過度に同調せず、客観的で率直な意見や対案を伝える

## コンテキスト
- **デザイン相談**は　`reference/case-study/` を参照
- **その他**は　`Knowledge/`を参照