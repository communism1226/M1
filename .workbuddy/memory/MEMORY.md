# 项目长期记忆 — 毛选 Xmind 整理（C:\Users\Administrator\Desktop\读书\Xmind）

## 项目结构
- `一/`、`三/`、`四/` 三卷 xmind 目录（2026-08 前二卷为手动整理，2026-08 起 AI 协作补完第一卷收尾三篇）。
- 卷四树源在 `.worktmp/v4/tree_*.json`；卷一树源在 `.worktmp/tree_v1_*.json`。
- 原文提取：`uploads/毛泽东选集.epub` → 按 ncx（ElementTree 迭代 navPoint）定位 `Text/Section01NN.xhtml` → 去标签存 `.worktmp/v1_*.txt`。

## GitHub 仓库与上传方式（重要）
- 仓库：`https://github.com/communism1226/M1`（main 分支），存毛选 xmind 读书笔记，按 `一/`、`三/`、`四/` 文件夹组织。当前已传：三/（40 个）、四/（70 个）；一/ 未传。
- **本环境 git 网络操作（clone/push/credential）会被沙箱挂起（SIGTERM）**，不可用。GitHub 交互一律走 Python urllib + REST API。
- 上传文件夹的可靠方法：`GH_TOKEN=<token> python .worktmp/upload_github_folder.py <repo> <本地目录> <远端文件夹名>`（Git Data API 单 commit 完成：blob→tree→commit→ref；默认删除根目录散落的同扩展名旧文件；删除条目必须带 mode/type/sha=null，否则 422）。
- Token 由用户提供（classic 或 fine-grained，需 Contents 读写权限），用完提醒用户到 GitHub 设置撤销。
- **用户学习状态**：正在学习 GitHub 基本操作（上传文件夹/删除文件），已讲解四条路对比（网页端 / GitHub Desktop / git 命令行 / API）。用户实战驱动，偏好图形界面（Desktop）优先于命令行，教学要结合其 M1 仓库实例。

## 毛选整理范式（2026-08-30 修正版）
- 节点必须是语序正常的完整论断句（主谓宾齐全、连接修饰到位），禁词语堆砌。
- 结构深浅交错：板块直挂叶子 / 判断句挂细节 / 判断→子判断→细节纵深并存，禁全篇均匀三层。
- 细节见 skill `maoxuan-xmind-note` 的 style-guide.md。
