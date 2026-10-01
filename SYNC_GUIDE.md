# GitHub 同步上游代码指南

## 适用场景
当你的仓库和目标仓库同属一个“根仓库”网络，导致 GitHub 网页端无法直接 Fork，也没有 "Sync fork" 按钮时，使用此方法强制同步目标仓库的最新代码。

**目标仓库：** `hugosantanna/clo-author`

## 操作步骤

1. 打开你自己的 GitHub 仓库主页。
2. 点击绿色的 **`<> Code`** 按钮。
3. 切换到 **Codespaces** 标签，点击 **Create codespace on main** (或 `+` 号) 打开网页终端。
4. 等待网页加载完成后，在下方的 Terminal (终端) 窗口中，依次复制并回车运行以下 4 行命令：

### 指令 1：添加原作者的仓库作为远程源 (命名为 hugo)
```bash
git remote add hugo https://github.com/hugosantanna/clo-author.git
git fetch hugo
git merge hugo/main --allow-unrelated-histories
git push origin main

5. 粘贴好之后，点击页面右上角的绿色按钮 **`Commit changes...`**。
6. 在弹出的窗口中，直接点击绿色的 **`Commit changes`** 确认保存。

完成！现在你的仓库里就会多出一个叫 `SYNC_GUIDE.md` 的文件。以后你只需要点开这个文件，就能随时复制里面的命令来更新代码了！
