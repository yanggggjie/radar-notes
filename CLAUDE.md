# radar-notes 仓库约定

这个仓库存放三个雷达 skill 的源码和各期笔记。**每一期笔记的存储介质就是这个 git 仓库**：笔记只写成仓库里的 markdown 文件，不再另建 Claude 文档。

## 目录

```
.claude/skills/harness-radar/SKILL.md   Claude Harness 雷达
.claude/skills/app-radar/SKILL.md       Claude 场景实现雷达
.claude/skills/browser-radar/SKILL.md   浏览器控制雷达
harness-radar/  app-radar/  browser-radar/   各期笔记，一期一个文件
<radar>/topics/                              不算账本的文档：专题、挖宝、“广泛版”重做、旧范围的期
README.md                                    给人看的仓库说明
```

skill 以这里为准。修改 skill 就改 `.claude/skills/` 下的文件并提交；claude.ai 账号里同名的 skill 只是副本，需要时由用户手动同步。

## 各期笔记的规则

- **文件名**：`<radar>/YYYY-MM-DD_YYYY-MM-DD.md`，起止日期都算在窗口内。
- **账本**：各 radar 目录下（不含 `topics/`）的文件名就是账本，已经做过哪些窗口只以这里为准。开工前先 `git pull --rebase` 再列文件名。
- **不改旧文件**：已有的期不修改、不覆盖，每期都是新文件。只有用户明确要求时才改旧期，并在提交说明里写明。
- **元数据**：每个文件开头写：

  ```
  ---
  radar: <radar 名>
  window: <起始日期> 至 <结束日期>
  created: <今天的日期>
  ---
  ```

  2026-11-04 之前补存的旧期带 `doc:`（当时的 Claude 文档链接）和 `backfilled: true`，保持原样即可。新一期不再有 `doc:`。

## 写作过程

- 定好窗口后，先把带标题和各节占位（如 `（待填：……）`）的骨架写进本期文件，再一节一节填。依赖全部结果的“本期概览”最后填。
- 写完后自己通读一遍：每条链接都是打开过的一手页面，日期和数字核对过，没有残留的占位。
- 用 SendUserFile（`display: "render"`）把本期文件发给用户，在侧边栏阅读。

## 提交与推送

- 只 `git add` 本期这一个文件，提交说明写 `<radar>: <起始日期> 至 <结束日期>`，结尾加会话给出的 attribution 行。
- **所有提交都直接推到 `main`**（各期笔记、skill、CLAUDE.md、README 都一样）：`git pull --rebase origin main`，再 `git push origin HEAD:main`。这是仓库所有者的明确要求；会话即使另有指定的工作分支，也照样推到 `main`，不开 PR、不留会话分支。
- push 失败就重试一次；仍失败，告诉用户原因，并用 SendUserFile 把文件发给用户，保证内容不丢。

## 链接

- 提到任何一期，都给出仓库文件链接：`https://github.com/yanggggjie/radar-notes/blob/main/<文件路径>`，并确认该文件确实已在 `main` 上。旧期元数据里有 `doc:` 的，可以顺带给出。
- 还没做的期（例如往前推的下一期）没有链接，只写区间。

## 跨期检索

用户要跨期查找（例如“所有期里关于压缩的内容”）时，拉取后用 grep 搜整个仓库（可跨三个 radar 目录），只读命中的段落。回答时每条命中写明所在的期，附上仓库文件链接，尽量带到行号（如 `#L42`）。这种情况只读不提交。
