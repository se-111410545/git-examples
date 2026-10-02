# Git Branch 使用教學

## 什麼是 Branch？

Branch（分支）讓你可以從主線（main）獨立開發，不影響別人。完成後再合併回去。

---

## 基本指令

### 1. 查看目前有哪些分支

```bash
git branch
```

`*` 號標示的是目前所在的分支。

查看遠端分支：

```bash
git branch -a
```

### 2. 建立新分支

```bash
git branch <branch-name>
```

### 3. 切換到指定分支

```bash
git checkout <branch-name>
```

### 4. 建立並同時切換

```bash
git checkout -b <branch-name>
```

### 5. 刪除分支

刪除本地分支：

```bash
git branch -d <branch-name>
```

強制刪除（未合併的分支）：

```bash
git branch -D <branch-name>
```

刪除遠端分支：

```bash
git push origin --delete <branch-name>
```

---

## 實際流程範例

### 情境：新增一個功能

```bash
git checkout main
git pull
git checkout -b feature/new-feature
```

修改完檔案後：

```bash
git add .
git commit -m "Add new feature"
```

推送到遠端：

```bash
git push origin feature/new-feature
```

再到 GitHub 上發 Pull Request（PR），審查後合併回 main。

---

## 合併分支

切回 main 後合併：

```bash
git checkout main
git merge <branch-name>
```

合併時若發生衝突，Git 手會提示衝突的檔案，手動修改後再：

```bash
git add .
git commit
```

---

## 常用進階指令

### 查看分支圖

```bash
git log --oneline --graph --all
```

### 重新命名分支

```bash
git branch -m <old-name> <new-name>
```

### 推送新分支到遠端並建立對應追蹤

```bash
git push -u origin <branch-name>
```

`-u` 是 `--set-upstream` 的縮寫，設定後之後只需要 `git push` 即可。

---

## 命名建議

- `feature/xxx`：新功能
- `fix/xxx`：修 bug
- `hotfix/xxx`：緊急修正
- `docs/xxx`：文件修改

例如：`feature/login`、`fix/crash-on-startup`

---

## 總結

| 指令 | 用途 |
| --- | --- |
| `git branch` | 列出本地分支 |
| `git branch <name>` | 建立分支 |
| `git checkout <name>` | 切換分支 |
| `git checkout -b <name>` | 建立並切換 |
| `git branch -d <name>` | 刪除分支 |
| `git merge <name>` | 合併分支 |
| `git push -u origin <name>` | 推送並設定追蹤 |