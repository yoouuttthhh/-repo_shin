# CLAUDE.md — -repo_shin

## このリポジトリの目的
デザイナーが「企画→Webサイト開発→立ち上げ」までの一連を学ぶ過程を記録し、
継続的にアップデートしていく個人の学習ログです。

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

## 各フォルダの役割

- **Knowledge/**：学んだ技術・知識の記録（GitHub運用、セミナー等）
- **Design/Scrap/**：Webデザインの実例収集と審美眼のすり合わせ記録
- **Development/Scrap-site/**：Scrap/のデータを表示するギャラリーサイトの実装
  （Next.js。`lib/`内で `../../Design/Scrap/entries` を読み込む）

---

## Claudeへのお願い

- **Knowledge/Seminars/** の内容は時系列で増えていくので、要約や傾向分析を
  頼まれたら日付順に読み込んで回答してください
- **Design/Scrap/taste-profile.md** は、デザイン相談の際に最初に参照すべき
  「好みの基準」です。新しいデザイン案件の相談を受けたら、まずここを
  読み込んでから提案してください
- **Design/Scrap/disagreements.md** は、意見が割れた事例集です。ここに
  蓄積された傾向も踏まえて、率直な意見を伝えてください（同調しすぎない）
- 各フォルダの内容が増えてきたら、定期的に傾向を要約し、該当する
  ファイル（taste-profile.md等）に反映することを提案してください
