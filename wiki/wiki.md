# wiki.md

## Homebrew
macOSのパッケージ管理ツール。iPhoneのApp Storeに相当するもの。
開発ツールをコマンド一行でインストール・アップデート・削除できる。

- **なぜ必要か**
  Node.jsなどApple標準外のツールを
  手軽にインストールするための土台

- **インストール**：
  ```zsh
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
  ```
- **使い方**：
  ```zsh
  brew install ツール名   # インストール
  brew update            # Homebrew自体を更新
  brew upgrade           # インストール済みツールを更新
  ```
- **関連**：Node.js / npm / Claude Code のインストールに必要

## nvm
Node.jsのバージョンを複数インストールして、プロジェクトごとに切り替えて使うためのツール。
スマホに複数のOSバージョンを入れておいて、アプリに合わせて使い分けるようなもの。

- **なぜ必要か**
  プロジェクトによって要求されるNode.jsのバージョンが異なるため、
  1つのバージョンだけ入れていると動かないプロジェクトが出てくる

- **インストール**：
  ```zsh
  curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
  ```

- **使い方**：
  ```zsh
  nvm install 20   # Node.js 20系をインストール
  nvm use 20       # Node.js 20系に切り替え
  nvm ls           # インストール済みバージョンの一覧
  ```
- **関連**
  Node.js / npm / Homebrew
