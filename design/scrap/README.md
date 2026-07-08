# design-scrapbook セットアップガイド

Webデザインスクラップを蓄積し、Claudeと審美眼をすり合わせながら、
最終的にGitHub上のmdを元にギャラリーサイトとして公開するための
最終構成と立ち上げ手順です。

---

## 1. design-scrapbook/ ファイル構成（最終版）

```
design-scrapbook/
├─ README.md                 ← 運用ルールの説明
├─ taxonomy.md               ← 分類基準・タグ一覧の定義
├─ taste-profile.md          ← すり合わせた「好みの言語化」蓄積（最重要）
├─ disagreements.md          ← 意見が割れた事例集
│
├─ entries/                  ← スクラップ本体（1件1md）
│   ├─ 2026-07-08_kagami.md
│   ├─ 2026-07-10_studio-anon.md
│   └─ ...
│
├─ assets/                   ← 元画像・変換後gif
│   ├─ 2026-07-08_kagami-hero.png
│   ├─ 2026-07-08_kagami-hero.gif
│   └─ ...
│
└─ site/                     ← ギャラリーサイト本体（Next.jsプロジェクト）
    ├─ app/
    │   ├─ page.tsx          ← ギャラリー一覧（フィルタ機能付き）
    │   ├─ entry/[slug]/
    │   │   └─ page.tsx      ← 個別エントリ詳細ページ
    │   └─ taste-profile/
    │       └─ page.tsx      ← taste-profile.mdの表示ページ
    ├─ lib/
    │   └─ entries.ts        ← entries/*.md を読み込むロジック
    ├─ package.json
    └─ next.config.js
```

**構成の考え方**
- `entries/` `assets/` `taxonomy.md` 等はデータそのもの。**サイトのコードとは独立**しており、サイトを作り直してもこのデータ資産はそのまま使い回せる
- `site/` はあくまで「entries/を表示するビューア」という位置づけ

---

## 2. taxonomy.md（分類基準）

```markdown
# taxonomy.md（分類基準）

## 業種（industry）
企画・制作・開発 / くらし・住まい・環境 / 飲料・食品・グルメ / デザイン・アート /
雑貨・家具・文具 / ファッション / 健康・医療・製薬 / 教育・学校 / 音楽 /
旅行・観光・宿泊 / PC・家電・電子機器 / 運輸・交通 / 金融・証券・保険 /
自動車・バイク / スポーツ・アウトドア / 美容・コスメ / 広告・出版 /
エンタメ・ゲーム / 複合商業施設 / 官公庁・特殊法人 / その他

## サイト種別（site_type）
コーポレートサイト / EC・WEBサービス / 採用サイト / 商品・製品紹介 /
サービス紹介 / 店舗・施設紹介 / 特設サイト / 記念・周年サイト /
ポートフォリオ / メディア・ポータル / ランディングページ(LP) /
ブランドサイト / サステナビリティ・SDGsサイト

## カラー（color）
white / gray / blue / navy / skyblue / beige / red / green / colorful /
black / yellow / orange / brown / pink / gold / pastel / purple

## トーン（tone）
鮮やか / 深い / くすんだ / 渋い / 明るい / 浅い / 暗い / 濁った /
強い / 柔らかい / 薄い / 重い

## デザイン印象（impression）
シンプル / 上品・エレガント / にぎやか / さわやか / 高級・リッチ /
かわいい・キュート / かっこいい・スタイリッシュ / 清潔感 / ポップ・カジュアル /
やさしい・ナチュラル / 堅実・誠実・信頼感 / クール / 未来・サイバー /
和風・レトロ / ミニマル / メガタイポグラフィ / コラージュ / 3Dグラフィック

## 機能・要素（elements）
メガメニュー / ドロワーメニュー / フルスクリーンナビ / アコーディオン /
カード型UI / スライド・カルーセル / 横スクロール / パララックス /
スクロール連動アクション / インフォグラフィック / クロストーク・座談会 /
実績紹介 / FAQ / 動画埋め込み / 縦書きテキスト / 多言語対応

## AI感症状（ai_pattern）※該当した場合のみ記載
blue-purple-gradient / cream-serif-terracotta / black-acid-green /
uniform-3col-cards / numbered-markers / glassmorphism /
inter-poppins-only / notosans-only / empty-buzzwords / uniform-fade-in-up
```

---

## 3. entries/ サンプルmd（最終版）

```markdown
---
title: "KAGAMI（教育DXサービス）コーポレートサイト"
url: https://jp.is-kagami.com/
date: 2026-07-08

industry: [教育・学校]
site_type: [サービス紹介, コーポレートサイト]
color: [blue, white]
tone: [明るい, 柔らかい]
impression: [堅実・誠実・信頼感, ポップ・カジュアル]
elements: [カード型UI, インフォグラフィック, 実績紹介]
ai_pattern: [blue-purple-gradient, uniform-3col-cards]

media: assets/2026-07-08_kagami-hero.png
motion_media: assets/2026-07-08_kagami-hero.gif
---

## サイトマップ（ページ構成）
- TOP（ロングスクロール構成、下層ページなし）
  - ヒーロー
  - 導入事例
  - 課題提起（マンネリ化／やりっぱなし）
  - サービス概要図解
  - 対象読者紹介
  - 解決策1・解決策2
  - 機能一覧
  - 利用可能な階層・シーン紹介
  - CTA／フッター
- ヘッダーナビ（推測）：特徴 / 事例 / 料金 / サービス概要 / 会社概要 / QA

## レスポンシブの変化点
- Desktop → Tablet：3〜4カラムのカードが2カラムに変化
- Tablet → SP：ハンバーガーメニューに切替、ヒーロー見出しが2行→3行に折返し
- 気になった点：SPでアイソメトリックイラストが縮小され、
  シグネチャー要素（タイル状の床）の視認性が下がっている

## よく使われているテキストのテイスト
- キャッチコピーの型：具体的な課題提起型（「マンネリ化」「やりっぱなし」等の
  固有の課題ワードを使用、抽象語ではない）
- 文体：ですます調中心、体言止めも一部使用
- 特徴的な言い回し：「◯◯を、まるごと解決」型の動詞締め

## 自分の見立て
（実際に見た第一印象をここに書く）

## Claudeの見立て（先入観なしの分析）

**全体印象**
青系グラデーション＋アイソメトリックイラストを基調にした、BtoB SaaSの
王道パターン。信頼感・清潔感は出ているが、同ジャンルのサービスサイトと
見分けがつきにくいタイプの構成。

**配色**
ベースは水色〜青のグラデーション。アクセントに濃紺、差し色はほぼなし。

**レイアウト**
ヒーローは中央〜左寄せ見出し＋右側アイソメトリック図版というSaaS系の
定番構成。以降のセクションも「見出し＋3〜4カラムのアイコンカード」の
反復で、セクション間のリズム変化が少ない。

**シグネチャー要素**
タイル状の幾何学床がヒーローにあるが、他セクションに波及していない。

**AI感の観点**
青系グラデーション・3〜4カラムカードの反復に該当。ただしコピーは
具体的な課題語を使っており、空虚ワード型には該当しない。

## 一致した点
（会話の中で埋める）

## 割れた点
（会話の中で埋める）

## 今回の学び
実在の制作会社によるサイトでも、配色・レイアウトの面ではAI感の
症状リストに複数該当する。「AI感=AIが作った証拠」ではなく、
「業界で無難に流通している定番パターンそのもの」と捉える方が正確。
```

---

## 4. GitHubリポジトリ作成〜サイト立ち上げ手順

### Step 1：リポジトリを作成する
1. GitHubで新規リポジトリ `design-scrapbook` を作成（Public/Privateはお好みで）
2. ローカルにクローン
```bash
git clone https://github.com/【あなたのアカウント名】/design-scrapbook.git
cd design-scrapbook
```

### Step 2：フォルダ構成を作る
```bash
mkdir entries assets site
touch README.md taxonomy.md taste-profile.md disagreements.md
```
上記2・3の内容を、それぞれ `taxonomy.md` と `entries/2026-07-08_kagami.md` として保存します。

### Step 3：初回コミット
```bash
git add .
git commit -m "初期構成: design-scrapbookのフォルダとサンプルエントリを追加"
git push origin main
```

### Step 4：Git LFSの設定（画像・gif容量対策）
スクショやgifは容量が大きくなりやすいため、Git LFSを使います。
```bash
git lfs install
git lfs track "assets/*.png"
git lfs track "assets/*.gif"
git add .gitattributes
git commit -m "Git LFSでassetsを管理"
git push
```

### Step 5：サイト（Next.js）を立ち上げる
```bash
cd site
npx create-next-app@latest . --typescript --app
npm install gray-matter
```
`gray-matter` はmdファイルのfrontmatterを解析するために使用します。

### Step 6：entries/を読み込むロジックを作る
`site/lib/entries.ts` に、`../entries/*.md` をすべて読み込み、
frontmatterと本文をパースして返す関数を実装します（Claude Codeに
「entries/ディレクトリの.mdファイルをすべて読み込み、frontmatterと
本文を返すNext.js用の関数を作って」と依頼すれば生成できます）。

### Step 7：ギャラリーページ・詳細ページを実装
- `app/page.tsx`：entries一覧をカードグリッドで表示、タグでフィルタ
- `app/entry/[slug]/page.tsx`：個別エントリの詳細表示
- `app/taste-profile/page.tsx`：taste-profile.mdをそのまま表示

これも前回のモックアップ（カードグリッド＋詳細ページ）をClaude Codeに
見せながら「このレイアウトで実装して」と依頼すれば、Figma MCPを介さずとも
直接コード化できます。

### Step 8：ローカル確認
```bash
npm run dev
```
`http://localhost:3000` でギャラリーが表示されることを確認します。

### Step 9：公開（Vercelが最も手軽）
1. [vercel.com](https://vercel.com) でGitHubアカウント連携
2. `design-scrapbook` リポジトリをインポート（Root Directoryを `site` に指定）
3. デプロイを実行 → 自動的に公開URLが発行される

### Step 10：以後の運用フロー
```bash
# 新しいスクラップを追加するたび
git add entries/新規ファイル.md assets/新規画像
git commit -m "追加: ○○社サイトのスクラップ"
git push
```
Vercelと連携していれば、pushするだけで自動的にサイトが再ビルドされ、
新しいエントリがギャラリーに反映されます。

---

## 運用サイクルの目安

```
週次：気になったサイトを2〜3件スクラップ（entries/に追加してpush）
月次：Claudeにentries全体を読ませ、taste-profile.mdを更新
       ＋ disagreements.mdから見えた傾向を1行で追記
```
