# -repo_shin

デザイナーとしての学習記録・成長の軌跡を残すリポジトリです。
「企画→Webサイト開発→立ち上げ」までの一連を学ぶ過程を記録し、
継続的にアップデートしていきます。

---

## -repo_shinの/ファイル構成

```
-repo_shin/
├─ README.md                      # リポジトリ全体の目的・地図
├─ CLAUDE.md                      # Claude用リポジトリ説明書
│
├─ checklist/                     # ツール・環境の使い方ナレッジ
│  └─ accessibility-checklist.md  # ウェブアクセシビリティのチェックリスト（WCAG 2.0）
│
└─ Knowledge/                     # ツール・環境の使い方ナレッジ
   ├─ github-knowledge.md
   ├─ seminars/                   # セミナー・勉強会の記録
   │  ├─ seminar-template.md
   │  └─ yyyy-mm-dd_xxxxxx.md
   │
   └─ reference/                  # 参考デザイン
      ├─ README.md                # このフォルダーの目的・地図
      ├─ CLAUDE.md                # Claude用フォルダー説明書
      ├─ reference-category.md    # 参考サイトの分類基準
      ├─ UI-dictionary.md         # ユーザーインターフェースの分類基準
      ├─ web-accessibility.md     # ウェブアクセシビリティの基準（WCAG 2.0）
      │
      ├─ case-study/              # 参考サイトの事例研究md
      │  └─ yyyy-mm-dd_xxxxxx.md
      │
      ├─ src/                     # reference/の画像などのアセット
      │  ├─ yyyy-mm-dd_xxxxxx.gif
      │  └─ yyyy-mm-dd_xxxxxx.png
      │
      └─ development/             # reference/を表示するサイト実装
         ├─ app/
         ├─ lib/
         └─ package.json
```

- `knowledge/` : Claude CodeとWebフルスタック開発を手伝うナレッジ
- `reference/` : デザイン知見

<!--　---

## 中身

- [GitHub運用ナレッジ](./Knowledge/github.md)
- [セミナー記録一覧](./Knowledge/Seminars/)
- [デザインスクラップ](./Design/Scrap/)
- [スクラップ閲覧サイト](./Development/Scrap-site/)　
