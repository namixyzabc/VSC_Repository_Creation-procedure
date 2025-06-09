GitHubで作成したリポジトリに、VSCodeで作成済みのコードをプッシュする手順を詳しく解説します。

## 🚀 全体の流れ

1. **ローカルリポジトリの初期化**
2. **GitHubリポジトリとの接続**
3. **ファイルのステージング**
4. **コミット**
5. **プッシュ**

---

## 📋 手順1: ローカルリポジトリの初期化

VSCodeでプロジェクトフォルダを開き、ターミナルで以下のコマンドを実行：

```bash
git init
```

**このコマンドの意味：**
- プロジェクトフォルダをGitリポジトリとして初期化
- `.git`フォルダが作成され、バージョン管理が開始される

---

## 📋 手順2: GitHubリポジトリとの接続

```bash
git remote add origin https://github.com/あなたのユーザー名/リポジトリ名.git
```

**このコマンドの意味：**
- `git remote add`：リモートリポジトリを追加
- `origin`：リモートリポジトリの名前（慣例的にorigin）
- `https://github.com/...`：GitHubで作成したリポジトリのURL

**接続確認：**
```bash
git remote -v
```
設定されたリモートリポジトリの一覧が表示されます。

---

## 📋 手順3: ファイルのステージング

すべてのファイルをステージング（コミット対象に追加）：

```bash
git add .
```

**このコマンドの意味：**
- `git add`：ファイルをステージングエリアに追加
- `.`：現在のディレクトリ以下のすべてのファイル

**特定のファイルのみ追加したい場合：**
```bash
git add ファイル名
git add src/main.js
```

---

## 📋 手順4: コミット

ステージングしたファイルをコミット：

```bash
git commit -m "Initial commit"
```

**このコマンドの意味：**
- `git commit`：ステージングされたファイルをコミット
- `-m`：コミットメッセージを指定
- `"Initial commit"`：初回コミットの一般的なメッセージ

---

## 📋 手順5: プッシュ

GitHubリポジトリにプッシュ：

```bash
git push -u origin main
```

**このコマンドの意味：**
- `git push`：ローカルの変更をリモートリポジトリに送信
- `-u`：上流ブランチを設定（初回のみ必要）
- `origin`：プッシュ先のリモートリポジトリ名
- `main`：プッシュするブランチ名

---

## 🔄 2回目以降のプッシュ

初回設定後は、以下の3ステップで更新できます：

```bash
# 1. ファイルをステージング
git add .

# 2. コミット
git commit -m "コミットメッセージ"

# 3. プッシュ（-u origin mainは不要）
git push
```

---

## 💡 VSCodeのGUI操作

VSCodeでは、コマンドラインを使わずにGUIでも操作できます：

1. **ソース管理タブ**をクリック（左サイドバーのブランチアイコン）
2. **変更されたファイル**の「+」ボタンでステージング
3. **コミットメッセージ**を入力
4. **コミット**ボタンをクリック
5. **プッシュ**ボタンをクリック

---

## ⚠️ よくあるエラーと対処法

### エラー1: リモートリポジトリが空でない
```bash
git pull origin main --allow-unrelated-histories
git push -u origin main
```

### エラー2: ブランチ名がmasterの場合
```bash
git branch -M main
git push -u origin main
```

### エラー3: 認証エラー
- GitHubのPersonal Access Tokenを使用
- またはSSH鍵を設定

---

## 📝 完全なコマンド例

```bash
# 1. リポジトリ初期化
git init

# 2. リモートリポジトリ追加
git remote add origin https://github.com/username/repository.git

# 3. すべてのファイルをステージング
git add .

# 4. 初回コミット
git commit -m "Initial commit"

# 5. メインブランチに名前変更（必要に応じて）
git branch -M main

# 6. プッシュ
git push -u origin main
```

この手順で、VSCodeで作成したコードを無事GitHubリポジトリにプッシュできます！
