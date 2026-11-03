# radar-notes

三个雷达 skill 的各期笔记存档。每期的阅读版是一份 Claude 文档，这里存一份内容相同的 markdown，用于跨期检索和让其他 agent 直接读取。

## 目录结构

```
harness-radar/   Claude Harness 雷达：Anthropic 人员署名的 harness 原理内容
app-radar/       Claude 场景实现雷达：带代码或详细技术报告的具体场景实现
browser-radar/   浏览器控制雷达：浏览器与电脑操作（computer use）原理
<radar>/topics/  不算账本的文档：专题、挖宝、“广泛版”重做、旧范围的期
```

## 规则

- 每期一个文件，文件名就是起止日期：`YYYY-MM-DD_YYYY-MM-DD.md`。
- 各 radar 目录下（不含 `topics/`）的文件名就是账本：已经做过哪些窗口，以这里为准，同时参考 Claude 文档标题。
- 已有文件不修改、不覆盖，每期都是新文件。
- 每个文件开头的元数据写明 radar 名、窗口和对应的 Claude 文档链接。

## 检索

```
git clone https://github.com/yanggggjie/radar-notes
grep -rn "压缩" radar-notes --include=*.md
```
