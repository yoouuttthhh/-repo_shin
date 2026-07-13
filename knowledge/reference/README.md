# reference/

Webデザインスクラップを蓄積し、Claudeと審美眼をすり合わせながら、
最終的にGitHub上のmdを元にギャラリーサイトとして公開するための
最終構成と立ち上げ手順です。

---

## reference/のファイル構成

```
   - reference/                # 参考デザイン
      ├─ README.md             # このフォルダーの目的・地図
      ├─ CLAUDE.md             # Claude用フォルダー説明書
      ├─ reference-category.md # 参考サイトの分類基準
      ├─ UI-dictionary.md      # ユーザーインターフェースの分類基準
      ├─ web-accessibility.md  # ウェブアクセシビリティの基準（WCAG 2.0）
      │
      ├─ case-study/           # 参考サイトの事例研究md
      │  └─ yyyy-mm-dd_xxxxxx.md
      │
      ├─ src/                  # reference/の画像などのアセット
      │  ├─ yyyy-mm-dd_xxxxxx.gif
      │  └─ yyyy-mm-dd_xxxxxx.png
      │
      └─ development/          # reference/を表示するサイト実装
         ├─ app/
         ├─ lib/
         └─ package.json
```

- `knowledge/` : Claude CodeとWebフルスタック開発を手伝うナレッジ
- `reference/` : デザイン知見