# Node.jsのインストール方法

## Windowsでのインストール方法

1. [Node.js公式ダウンロードページ](https://nodejs.org/ja/download/) にアクセスします。
2. 「Windows Installer (.msi)」のLTS（推奨版）をダウンロードします。
3. ダウンロードしたインストーラー（.msiファイル）をダブルクリックして起動します。
4. 画面の指示に従ってインストールを進めます。
5. インストール完了後、コマンドプロンプトを開き、以下のコマンドでバージョンを確認します。

```sh
node -v
npm -v
```

---

## Macでのインストール方法

### 方法1: Homebrewを使う（推奨）

1. Homebrewがインストールされていない場合は、以下のコマンドでインストールします。

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

2. HomebrewでNode.jsをインストールします。

```sh
brew install node
```

3. インストール完了後、以下のコマンドでバージョンを確認します。

```sh
node -v
npm -v
```

### 方法2: 公式サイトからインストール

1. [Node.js公式ダウンロードページ](https://nodejs.org/ja/download/) にアクセスします。
2. 「macOS Installer (.pkg)」をダウンロードして実行します。
3. 画面の指示に従ってインストールします。
4. ターミナルで以下のコマンドを実行し、バージョンを確認します。

```sh
node -v
npm -v
```


どちらのOSでも、インストール後に`node -v`と`npm -v`でバージョンが表示されれば正常にインストールされています。


<br>
<br>

# Gitのインストール方法

## Windowsでのインストール方法

1. [Git公式ダウンロードページ](https://git-scm.com/download/win) にアクセスします。
2. インストーラー（.exeファイル）が自動的にダウンロードされます。
3. ダウンロードしたインストーラーをダブルクリックして起動します。
4. 画面の指示に従ってインストールを進めます（特にこだわりがなければデフォルト設定で問題ありません）。
5. インストール完了後、コマンドプロンプトまたはGit Bashを開き、以下のコマンドでバージョンを確認します。

```sh
git --version
```

---

## Macでのインストール方法

### 方法1: Homebrewを使う（推奨）

1. Homebrewがインストールされていない場合は、以下のコマンドでインストールします。

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

2. HomebrewでGitをインストールします。

```sh
brew install git
```

3. インストール完了後、以下のコマンドでバージョンを確認します。

```sh
git --version
```

### 方法2: Xcodeコマンドラインツールを使う

1. ターミナルを開き、以下のコマンドを実行します。

```sh
xcode-select --install
```

2. 画面の指示に従ってインストールします。
3. インストール完了後、以下のコマンドでバージョンを確認します。

```sh
git --version
```


どちらのOSでも、インストール後に`git --version`でバージョンが表示されれば正常にインストールされています。



<br>
<br>

# Playwright MCP環境準備
1. 任意の作業フォルダを準備します（どこでも大丈夫です）

```sh
~ % mkdir workspace
```

2. 作成したフォルダに移動して、Playwright MCPのリポジトリをcloneします

```sh
//workspaceフォルダに移動する
~ % cd workspace

//playwright MCPをcloneする
workspace % git clone https://github.com/microsoft/playwright-mcp.git
```

3. playwright mpcのパッケージをインストールします

```sh
//playwright-mcpフォルダが作成されているはずなので、そこに移動します
workspace % cd playwright-mcp

//playwright-mcpフォルダで以下を実行
playwright-mcp % npm install
```

<br>
<br>

# CursorでPlaywright MCPを使えるようにする
1. Cursorを開きます

2. Cursor > 基本設定 > Cursor Settingを開きます

3. サイドメニューのMCPを選択します

4. 「Add new global MCP server」を押下

5. mpc.jsonファイルが開くので、以下を貼り付け保存します

```json
{
    "mcpServers": {
      "playwright-mcp": {
        "command": "npx",
        "args": [
          "@playwright/mcp@latest"
        ]
      }
    }
  }

```

6. playwright-mcpの横が緑になっていればOK

7. 最後に今から実施するhands-onで作業するフォルダを作成しておきましょう

```sh
//workspaceフォルダの下に作業用フォルダを作成する
workspace % mkdir playwright-mcp-hands-on
```