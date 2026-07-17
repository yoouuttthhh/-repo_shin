# md.md

## スタイルルール

### 見出し
- 一番最初の1行は `# ファイル名.拡張子` にする（H1の扱い）
- H2は `##` で表示する
- H2の下層は `###`
- H3の下層は `**内容**`
- 情報の下層が足りない場合は `###` などを省略してもOK
- `##` には `1.` `2.` などの番号をつけない


### リスト・テキスト
- `# ファイル名.拡張子` の下には目標を２行以内で記載
- リストでまとめるときは `-` を使う
- ファイル・ディレクトリ・コマンドは `` ` `` で囲む
- 外部リンクは `[CLAUDE.md](./CLAUDE.md)` 形式にする


### 区切り・間隔
- `##` 単位の間は2回改行する
- `---` は禁止


### ファイル構造
- ファイル構造を表す場合は以下のWBS形式を使う

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

### テーブル
- コマンド集などの場合はテーブル化する

| やること | コマンド | 説明 |
|---|---|---|
| フォルダーに移動する | `cd /path/to/your-repo` | 指定したフォルダーに移動する |
| VS Codeを現在フォルダーに切り替える | `code -r .` | 今開いているウィンドウをこのフォルダーに切り替える |
| VS Codeを新しいウィンドウで開く | `code .` | 新しいウィンドウでVS Codeを開く |