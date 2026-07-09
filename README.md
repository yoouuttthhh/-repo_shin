# -repo_shin

デザイナーとしての学習記録・成長の軌跡を残すリポジトリです。
「企画→Webサイト開発→立ち上げ」までの一連を学ぶ過程を記録し、
継続的にアップデートしていきます。

---

## ファイル構成

```
-repo_shin/
├─ README.md
├─ CLAUDE.md
│
├─ Knowledge/                  ← 学びの記録
│   ├─ github.md
│   └─ Seminars/
│       ├─ sample.md           ← セミナー記録の雛形
│       ├─ 2026-07-08_XXXXXXX.md
│       └─ ...
│
├─ Design/
│   └─ Scrap/                  ← デザイン観察記録
│       ├─ README.md
│       ├─ taxonomy.md
│       ├─ taste-profile.md
│       ├─ disagreements.md
│       ├─ entries/
│       └─ assets/
│
└─ Development/
    └─ Scrap-site/              ← Scrap/を表示するサイト実装
        ├─ app/
        ├─ lib/
        └─ package.json
```

---

## 中身

- [GitHub運用ナレッジ](./Knowledge/github.md)
- [セミナー記録一覧](./Knowledge/Seminars/)
- [デザインスクラップ](./Design/Scrap/)
- [スクラップ閲覧サイト](./Development/Scrap-site/)

---

## 運用ルール

- セミナー参加後はその日のうちに `Knowledge/Seminars/YYYY-MM-DD_セミナー名.md` を作成
  （雛形は `Knowledge/Seminars/sample.md` を複製して使う）
- デザインスクラップは週次で2〜3件 `Design/Scrap/entries/` に追加
- 月次で `Design/Scrap/taste-profile.md` をClaudeと壁打ちして更新
