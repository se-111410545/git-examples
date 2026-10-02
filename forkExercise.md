# Fork 練習紀錄

## 練習目標

學習完整的 Fork → Clone → Branch → Commit → Push → Pull Request → Merge 流程。

## 練習步驟紀錄

### 1. Fork
- 到老師的 repo：`https://github.com/se-111410545/git-examples`
- 按右上角 Fork → fork 到自己的帳號

### 2. Clone Fork 下來
```bash
git clone git@github.com:NaroFeng/git-examples.git my-fork-examples
cd my-fork-examples
```

### 3. 設定 upstream
```bash
git remote add upstream git@github.com:se-111410545/git-examples.git
git remote -v
```

### 4. 從 upstream 開新分支（避免夾帶自己的 commit）
```bash
git fetch upstream
git checkout -b feat/fork-tutorial upstream/main
```

### 5. 修改並 commit
```bash
# 新增檔案
git add .
git commit -m "Add fork tutorial"
```

### 6. Push 上去
```bash
git push origin feat/fork-tutorial
```

### 7. 發 Pull Request
- 到 GitHub NaroFeng/git-examples 頁面
- 按 Compare & pull request
- base 選 se-111410545/git-examples / main
- compare 選 feat/fork-tutorial
- 發 PR

## 學到的事

- Fork 是「複製別人的 repo 到自己帳號」，讓你有完整 push 權限
- 不能直接 clone 老師的 repo 來發 PR，必須先 fork
- 用 `upstream` 跟 `origin` 分開管理「老師的」跟「自己的」repo
- 從 `upstream/main` 開分支才不會夾帶自己 main 上多餘的 commit
- PR 流程的核心是「Code Review」，確保程式碼品質