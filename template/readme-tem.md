# readme-tem.md
README.mdを新規作成する時の構成テンプレート。
スタイルルールは `template/template-style.md` に従うこと。


## 使い方
- 新しいリポジトリにREADME.mdを作成する時にこのテンプレートを使う
- 各セクションの「何を書くか」の説明を参考に内容を埋める


## 制約事項・禁止事項
- 新しいリポジトリやフォルダーにCLAUDE.mdを作成する時にこのテンプレートを使う
- 各セクションの「何を書くか」の説明を参考に内容を埋める


## 出力形式
このルールに従って以下の構成でREADME.mdを作成する


**出力の順番**
- `# ファイル名` ：ファイル名をそのまま記載
- 何のためのフォルダーか・解決する問題を1〜3行で記載
- `## 使い方` ：このリポジトリの使い方・更新ルールを箇条書きで記載
- `## ファイル構成` ：該当するフォルダー下層構成をWBS形式のツリーで記載
- `## 関連リンク` ：関連するリポジトリ・ドキュメントのリンクを記載（任意）


**出力の例**
```
# README.md
デザイナーとしての学習記録・成長の軌跡を残すフォルダー。
「企画→Webサイト開発→立ち上げ」までの一連を学ぶ過程を記録し、
継続的にアップデートしていく。


## 使い方
- セミナー参加後はその日のうちに `seminars/yyyy-mm-dd_セミナー名.md` を作成する
- 新しい用語を学んだら `wiki/wiki.md` に追記する
- ファイル構成が変わったらこのREADME.mdと `CLAUDE.md` を更新する


## ファイル構成

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
├─ prj-reference/                 # 参考デザイン
│  ├─ CLAUDE.md                   # Claude用フォルダー説明書
│  ├─ reference-category.md       # 参考サイトの分類基準
│  ├─ UI-dictionary.md            # ユーザーインターフェースの分類基準
│  └─ web-accessibility.md        # ウェブアクセシビリティの基準（WCAG 2.0）
│
├─ prompt/                        # プロンプト置き場
│  ├─ asana-tem.md                # Asana用プロンプトテンプレート
│  ├─ claude-tem.md               # Claude用プロンプトテンプレート
│  └─ readme-tem.md               # README用プロンプトテンプレート
│
├─ seminars/                      # セミナー・勉強会の記録
│  ├─ CLAUDE.md                   # セミナー要約プロンプトテンプレート
│  └─ yyyy-mm-dd_セミナー名.md
│
└─ wiki/                          # 開発用語Wiki
   ├─ CLAUDE.md                   # wiki追加用プロンプトテンプレート
   └─ wiki.md                     # 開発用語集


## 関連リンク
- [CLAUDE.md](./CLAUDE.md)
```