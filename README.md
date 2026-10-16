# Agent Reply Footer

让 Codex 每次答复，都说清楚做了什么、接下来做什么。

```text
已完成：文档已整理好，排版也检查过了
下一步：确认姓名和日期后就可以使用
```

## 复制这句话，安装并启用

```text
请从 https://github.com/StarSure/agent-reply-footer 安装 agent-reply-footer 技能，在全局和当前项目启用，保留其他规则，并从当前对话开始使用。
```

只想在当前项目使用？把“在全局和当前项目启用”改成“只在当前项目启用”即可。

## 它会做什么

把收尾规则写入 `AGENTS.md`，以后每轮最终答复都用“已完成 / 下一步”交代结果。进度更新不必重复，任务结束了就自然说明，不硬凑后续，也不为写这两行增加额外检查。

技能只在配置或更新规则时使用，日常回复无需反复调用。启用时只修改相关段落，保留你的其他规则。

## 更新与移除

更新技能后，请 Codex 将新版规则同步到你需要的范围。其他已有对话不会因此全部自动更新，可在对应对话中说：

```text
请重新读取全局和当前项目 AGENTS.md 中的收尾规则，从本轮起采用新版，保留当前任务进度。
```

想停用时，发送：

```text
使用 $agent-reply-footer，移除全局和当前项目 AGENTS.md 中这套收尾规则及其更新约定，保留其他内容，当前对话也停止使用。
```

删除技能文件夹本身，不会移除已写入 `AGENTS.md` 的规则。

## 想先看看内容

- [技能说明](skills/agent-reply-footer/SKILL.md)
- [完整规则](skills/agent-reply-footer/assets/reply-footer-rules.md)

适用于使用 `AGENTS.md` 的 Codex 工作流。采用 [MIT License](LICENSE)。
