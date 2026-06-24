# git-test
git软件练习仓库

# Git 使用教程

## 基础配置

```bash
# 设置用户名和邮箱
git config --global user.name "你的名字"
git config --global user.email "你的邮箱"

# 查看配置
git config --list
```

## 创建与克隆

```bash
# 初始化本地仓库
git init

# 克隆远程仓库
git clone https://github.com/用户名/仓库名.git
```

## 基础操作

```bash
# 查看状态
git status

# 添加文件到暂存区
git add 文件名          # 添加单个文件
git add .              # 添加所有文件

# 提交更改
git commit -m "提交说明"

# 查看提交历史
git log
git log --oneline      # 简洁模式
```

## 分支管理

```bash
# 查看分支
git branch              # 本地分支
git branch -a           # 所有分支（包括远程）

# 创建分支
git branch 分支名

# 切换分支
git checkout 分支名
git switch 分支名        # 新版命令

# 创建并切换
git checkout -b 分支名
git switch -c 分支名

# 合并分支
git merge 分支名

# 删除分支
git branch -d 分支名
```

## 远程操作

```bash
# 查看远程仓库
git remote -v

# 添加远程仓库
git remote add origin https://github.com/用户名/仓库名.git

# 推送代码
git push origin 分支名
git push -u origin 分支名   # 首次推送并设置上游

# 拉取代码
git pull origin 分支名

# 拉取但不合并
git fetch origin
```

## 撤销与回退

```bash
# 撤销工作区的修改（未暂存）
git checkout -- 文件名
git restore 文件名

# 撤销暂存（已 add 但未 commit）
git reset HEAD 文件名
git restore --staged 文件名

# 回退到指定版本
git reset --hard 提交ID
git reset --soft 提交ID    # 保留修改
git reset --mixed 提交ID   # 保留工作区修改
```

## 常用场景

```bash
# 完整推送流程
git add .
git commit -m "提交信息"
git push origin main

# 完整拉取流程
git pull origin main

# 查看差异
git diff                # 工作区 vs 暂存区
git diff HEAD           # 工作区 vs 最新提交
git diff --cached       # 暂存区 vs 最新提交

# 储藏工作区修改
git stash               # 暂存当前修改
git stash pop           # 恢复暂存的修改
git stash list          # 查看储藏列表

# 标签管理
git tag v1.0            # 创建标签
git tag                  # 查看标签
git push origin v1.0     # 推送标签
```

## 注意事项

- 提交信息要清晰，描述做了什么修改
- 推送前先 `git pull` 拉取最新代码，避免冲突
- `.gitignore` 文件可忽略不需要跟踪的文件
- 敏感信息不要提交到仓库
