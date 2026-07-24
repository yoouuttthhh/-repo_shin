# CHANGELOG.md
`-repo_shin`のファイル・フォルダー管理の変更履歴。
参照：[CHANGELOG-tem.md](./Template/CHANGELOG-tem.md)


## [Unreleased]


## [2026-07-24]

### Added
- `Template/Sitemap/sitemap-research.md` を新規作成（プロジェクト開始時のゼロからのサイトマップ調査専用。既存サイトのURLから調査するプロンプトと精度を上げる方法を集約）

### Changed
- `Template/Sitemap/sitemap-tem.md` を全面改訂（理由：サイト運営中の改修依頼に対応する用途に特化させ、調査系の内容は`sitemap-research.md`に分離するため）
  - 出力形式を「現在（常に最新の状態・上書き）」と「バージョン履歴（差分のみ・追記）」の2層構造に変更（理由：更新のたびに全ページを複製するとファイルが際限なく肥大化するため）
  - 「使い方」「背景・前提条件」「制約事項・禁止事項」のテキストを、AIが手順として読み取りやすい番号付き手順・表形式に書き直し
- `Template/template-style.md` に「バージョン管理」「スナップショット型の更新履歴」セクションを追加（理由：sitemap-tem.mdで運用していたバージョン管理・差分タグの記法を他のテンプレートでも使えるよう一般化するため）
- `CLAUDE.md` のファイル構成に `sitemap-research.md` の追加を反映

### Removed
- `Template/Sitemap/sitema-sample.xlsx` を削除（理由：サイトマップ管理をmd・CSVの2形式に統一し、XLSXを廃止したため）