---
name: submit-github
description: 将项目提交并推送到 GitHub 远程仓库（git@github.com:15zzz/czr）. Use when the user asks to 提交到github, 提交github, 上传github, push github, or 推送到 GitHub. Covers git add, commit, github remote setup, and push via SSH for this static site repo.
---

# 提交到 GitHub（commit + push 到 GitHub）

把当前项目提交并推送到 GitHub 仓库：
`https://github.com/15zzz/czr`（SSH 地址：`git@github.com:15zzz/czr.git`，公钥已配置）

本仓库是纯静态 HTML/CSS 项目（无构建、无测试、无 lint）。

## 步骤

1. **先记录提示词**（项目强制规则）：在任务开始前，把本次执行时间、模型、提示词原文
   追加写入 `chen_prompt.md`（追加模式，绝不覆盖原有内容）。可参考文件中已有条目的格式：

   ```
   ## <yyyy-MM-dd HH:mm:ss zzz>
   - 模型：trae
   - 提示词原文：

   ```
   <prompt 原文>
   ```
   ```

2. **检查状态**：`git status` 和 `git diff`，确认要提交的内容。忽略无关的临时文件；
   绝不提交密钥或敏感信息。

3. **确认远程仓库**：`git remote -v`
   - GitHub 使用独立的 `github` 远程名，与 Gitee 的 `origin` 并存，互不影响。
   - 若 `github` 不存在，则添加（使用 SSH，公钥已配置）：
     `git remote add github git@github.com:15zzz/czr.git`
   - 若 `github` 已存在但地址不对，则更新：
     `git remote set-url github git@github.com:15zzz/czr.git`
   - 首次连接 GitHub 如提示主机密钥确认，可先执行：
     `ssh-keyscan github.com >> ~/.ssh/known_hosts`

4. **暂存并提交**：`git add -A`，然后写一句简洁的中文提交信息，例如：
   `git commit -m "提交项目更新"`

5. **推送**：`git push -u github master`
   （若当前分支不是 `master`，先 `git branch --show-current` 确认，再推送对应分支；
   若 GitHub 远端默认分支为 `main`，按远端实际分支推送或重命名本地分支。）

6. **确认结果**：再次运行 `git status` / `git log --oneline -3`，向用户报告提交与推送结果。

## 注意

- 仅在用户明确要求提交到 GitHub 时执行；不要主动提交。
- 本机 Git 的 HTTPS 辅助程序缺失，**必须使用 SSH 地址** `git@github.com:15zzz/czr.git` 推送，不要用 HTTPS。
- 推送 GitHub 不影响 Gitee 的 `origin` 远程；如需同时推送两个远程，分别执行 `git push origin master` 和 `git push github master`。
- 提交信息保持中文、简洁，与本仓库已有风格一致。
