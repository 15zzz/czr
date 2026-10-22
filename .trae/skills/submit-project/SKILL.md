---
name: submit-project
description: 将项目提交并推送到 Gitee 远程仓库. Use when the user asks to 提交项目, 提交代码, 上传, git commit, push, or 推送到 Gitee. Covers git add, commit, remote setup, and push for this static site repo.
---

# 提交项目（commit + push 到 Gitee）

把当前项目提交并推送到 Gitee 仓库：
`https://gitee.com/chen-zhuoran012/advanced-web-pages1012czr`

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
   - 若 `origin` 不存在，则添加：
     `git remote add origin https://gitee.com/chen-zhuoran012/advanced-web-pages1012czr.git`
   - 若 `origin` 已存在但地址不对，则更新：
     `git remote set-url origin https://gitee.com/chen-zhuoran012/advanced-web-pages1012czr.git`

4. **暂存并提交**：`git add -A`，然后写一句简洁的中文提交信息，例如：
   `git commit -m "提交项目更新"`

5. **推送**：`git push -u origin master`
   （若当前分支不是 `master`，先 `git branch --show-current` 确认，再推送对应分支。）

6. **确认结果**：再次运行 `git status` / `git log --oneline -3`，向用户报告提交与推送结果。

## 注意

- 仅在用户明确要求提交时执行；不要主动提交。
- 首次推送到新仓库可能需要在 Gitee 上配置账号凭据（HTTPS 用户名/密码或令牌）。
- 提交信息保持中文、简洁，与本仓库已有风格一致。
