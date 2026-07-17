# github.md
design-scrapbookのセットアップ時に学んだ、GitHub運用の基礎知識まとめ。


## 1. クローンできない時のチェックリスト

### エラー別の原因

| エラー内容 | 原因 |
|---|---|
| `Authentication failed` / `Invalid username or token` | パスワード認証は廃止済み。Personal Access Token（PAT）かSSH鍵が必要 |
| `git: command not found` | Gitがインストールされていない |
| `Repository not found` | URLのタイプミス、またはPrivateリポジトリへのアクセス権がない |
| `fatal: destination path 'xxx' already exists` | 同名フォルダがすでに存在している |
| `No such file or directory` | コマンド中のパス・URLが正しくない、プレースホルダーの置き換え忘れ、全角文字混入など |

### 基本確認コマンド
```bash
git --version        # Gitが使えるか確認
git remote -v        # 今どのリポジトリと繋がっているか確認
git status           # 今の変更状況を確認
```


## 2. GitHub認証の2つの方法

パスワード認証は使えないため、以下のどちらかが必要。

### 方法A：Personal Access Token（PAT）― 手軽
1. GitHub → 右上アイコン → **Settings**
2. **Developer settings** → **Personal access tokens** → **Tokens (classic)**
3. **Generate new token (classic)**
4. スコープに **repo** をチェック
5. 発行された `ghp_...` の文字列をコピーして保管（再表示不可）
6. clone/push時、Password欄に**パスワードの代わりにこのトークンを入力**

### 方法B：SSH鍵 ― 毎回の入力が不要になる
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
# 保存先を聞かれたら基本Enterのみでよい
# passphraseは空欄のままEnterでも可

cat ~/.ssh/id_ed25519.pub   # 表示された公開鍵をコピー
```
GitHub → **Settings → SSH and GPG keys → New SSH key** に貼り付け。

以後のURLはSSH形式に変更：
```bash
git clone git@github.com:ユーザー名/リポジトリ名.git
```

## 3. git add → commit → push の3段階

ローカルとGitHubの内容がズレる原因の多くは、この3段階のどこかで止まっていること。

```
[ローカル作業フォルダ]
   ↓ git add          （変更をステージに上げる）
[ステージ]
   ↓ git commit -m "説明"   （履歴として確定）
[ローカルのコミット履歴]
   ↓ git push          （GitHubへ送信）
[GitHub（リモート）]
```

日常的な操作はこの3行セット：
```bash
git add .
git commit -m "変更内容の説明"
git push
```

`git status` で「Changes not staged for commit」と出ていたら、まだ`add`していない証拠。


## 4. ローカルフォルダ名とリポジトリ名の関係

- **Gitはフォルダ名を見ていない。** 接続先は`git remote -v`で確認できるURLだけで決まる
- フォルダ名を変更しても、`.git`フォルダ（隠しフォルダ）さえ中にあれば接続は保たれる
  ```bash
  mv 現在のフォルダ名 新しいフォルダ名
  cd 新しいフォルダ名
  git remote -v   # 変わらず同じURLが表示されればOK
  ```
- ただし、**複数リポジトリを並行して扱う場合は、フォルダ名とリポジトリ名を一致させておいた方が混乱が少ない**（技術的には必須ではないが、運用上のおすすめ）


## 5. リポジトリを新規作成するタイミング

**「バージョン管理の単位を分けたいもの」ごとに新規作成する**のが基本原則。

| ケース | 新規作成するか |
|---|---|
| 新しいWeb制作案件（project-root）を始める | ◎ 作る |
| design-scrapbookのような継続的に育てるナレッジ | ◎ 作る |
| プロジェクトを横断する共有リソース（design-ops等） | ◎ 作る |
| 1案件内でデザイン用・開発用ドキュメントを分けたい | △ 分けない。同じリポジトリ内のフォルダ分けで十分 |
| ちょっとした検証・お試し | ○ 作ってもよいが、使い終わったら削除 or アーカイブ |

目安：
```
1案件 = 1リポジトリ
1継続的な個人ナレッジ = 1リポジトリ
1チーム共有資産 = 1リポジトリ
```

---

## 6. トラブル時の基本切り分け手順

1. `git --version` でGit自体が使えるか確認
2. `git remote -v` で接続先URLが正しいか確認
3. `git status` で今の変更状況（add/commit/push漏れがないか）確認
4. エラーメッセージが出たら、**その場でコピーしてそのまま検索・相談する**（推測で対処しない）
5. ターミナルの出力結果をそのままコピペで再実行してしまうと、意図しないコマンドとして実行されエラーになることがあるので注意

---

## 7. ゼロから始める場合の全体フロー（新規アカウント想定）

新しくGitHubアカウントを作った直後から、複数リポジトリを使い分けられる
ようになるまでの流れ。VS Code派・ターミナル派どちらでも進められるよう
両方の手順を併記する。

### Step 1：GitHubアカウント作成
1. https://github.com にアクセスし、**Sign up** からアカウント作成
2. メールアドレス・ユーザー名・パスワードを設定
3. 確認メールのリンクをクリックして本登録完了

### Step 2：Gitの初期設定（ローカル側・最初の1回だけ）
新しいMacやアカウントで初めてGitを使う場合、自分の名前とメールアドレスを
Gitに教えておく必要がある。

```bash
git config --global user.name "自分の名前"
git config --global user.email "GitHubに登録したメールアドレス"
```

### Step 3：認証方法を用意する
前述の「2. GitHub認証の2つの方法」を参照し、PATかSSH鍵のどちらかを
事前に用意しておく（この後の全操作で必要になる）。

---

## 8. リポジトリ作成〜ローカル連携（2つのやり方）

新しいリポジトリを作り、ローカルフォルダと繋げるまでの手順。
「GitHub上に先に作る」パターンと「ローカルに先に作る」パターンの
2通りがある。

### パターンA：GitHub上で先にリポジトリを作る（初心者向け・おすすめ）

**GitHub側の操作**
1. GitHub右上の **+** → **New repository**
2. Repository name を入力（例：`my-new-project`）
3. Public / Private を選択
4. **Add a README file** にチェックを入れておく（空リポジトリを避けられる）
5. **Create repository** をクリック

**ローカルへの連携（ターミナルの場合）**
```bash
cd 作業したい場所（例：~/Documents）
git clone https://github.com/ユーザー名/my-new-project.git
cd my-new-project
```

**ローカルへの連携（VS Codeの場合）**
1. VS Codeを開き、`Cmd+Shift+P` でコマンドパレットを開く
2. **Git: Clone** と入力して選択
3. GitHubのリポジトリURLを貼り付け、またはGitHubアカウント連携済みなら
   一覧から選択
4. 保存先フォルダを選ぶ
5. 「開きますか？」と聞かれたら **Open** を選択

### パターンB：ローカルに先にフォルダを作る場合

**ターミナルの場合**
```bash
mkdir my-new-project
cd my-new-project
git init
git add .
git commit -m "初回コミット"
```
GitHub側で空のリポジトリ（READMEなし）を作成後、以下でリモートと接続：
```bash
git remote add origin https://github.com/ユーザー名/my-new-project.git
git branch -M main
git push -u origin main
```

**VS Codeの場合**
1. 作業したいフォルダをVS Codeで開く（**File → Open Folder**）
2. 左サイドバーのソース管理アイコン（分岐マークのアイコン）をクリック
3. **Initialize Repository** ボタンをクリック
4. ファイルを変更後、変更一覧の「+」でステージに追加
5. 上部のメッセージ欄にコミット内容を入力し、**Commit**
6. **Publish Branch** ボタンをクリック → GitHub上に新規リポジトリとして
   公開するか聞かれるので、リポジトリ名を確認して **Publish**


## 9. 複数リポジトリを使い分けてコミット・プッシュする方法

案件やプロジェクトが増えると、複数のリポジトリを行き来することになる。
ここで大事なのは、**「今どのフォルダ（=どのリポジトリ）にいるか」を
毎回意識すること**。

### ターミナルでの切り替え

```bash
cd ~/Documents/project-A     # プロジェクトAのフォルダに移動
git status                   # 念のため今の状態を確認
git add .
git commit -m "プロジェクトAの変更"
git push

cd ~/Documents/project-B     # プロジェクトBのフォルダに移動
git status                   # プロジェクトBに切り替わったか確認
git add .
git commit -m "プロジェクトBの変更"
git push
```

**ポイント**：`cd`で移動した直後は必ず`git status`か`git remote -v`で
「今どのリポジトリにいるか」を確認する習慣をつけると、誤って違う
プロジェクトにコミットしてしまう事故を防げる。

### VS Codeでの切り替え

VS Codeは**開いているフォルダ（ウィンドウ）＝1つのリポジトリ**という
対応関係になる。複数リポジトリを扱う場合は以下のいずれかの方法を使う。

**方法1：ウィンドウを切り替える**
- `File → Open Recent` から、作業したいプロジェクトのフォルダを選んで開き直す
- 現在開いているフォルダ名がウィンドウ上部・左上に表示されるので、
  作業前に必ず確認する

**方法2：複数ウィンドウを同時に開く**
- `File → New Window` で別窓を開き、そちらで別のフォルダを開く
- 画面を並べておけば、プロジェクトAとBを見比べながら作業できる

**コミット・プッシュの操作自体は共通**
1. 左サイドバーのソース管理アイコンを開く
2. 変更されたファイルが一覧表示される（今、開いているフォルダ＝リポジトリの変更のみ表示される）
3. 「+」でステージに追加（全部まとめてでも、1ファイルずつでも可）
4. 上部にコミットメッセージを入力し、`Cmd+Enter`でコミット
5. 下部または左下の同期ボタン（雲のアイコンや「Sync Changes」）をクリックしてプッシュ


## 10. 事故を防ぐための確認習慣

複数リポジトリを行き来するようになったら、以下を毎回のクセにしておくと安心。

- **ターミナル**：作業前に必ず `pwd`（今いる場所）と `git remote -v`（接続先）を確認
- **VS Code**：ウィンドウのタイトルバー、またはエクスプローラー最上部のフォルダ名を確認
- コミットメッセージには、内容が分かる説明を必ず入れる（「update」等の曖昧な文言は避ける）
- 迷った時は `git status` を打つ。今の状態（変更有無・ブランチ・同期状況）が一目でわかる
