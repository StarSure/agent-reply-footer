# Agent Reply Footer · 通用回复收尾规则

## 一键安装并启用

复制下面这一句话发给 Codex，即可依次安装技能、写入规则，并在当前对话采用：

```text
请使用 $skill-installer 从 https://github.com/StarSure/agent-reply-footer 安装 skills/agent-reply-footer（已安装则直接使用），随后读取该技能的 SKILL.md，按其说明将通用收尾规则和更新约定写入我的全局及当前项目 AGENTS.md，替换旧收尾规则、保留其他内容，并从本轮起立即应用于当前对话。
```

这条指令会更新全局及当前项目的规则；如只想在当前项目使用，将“我的全局及当前项目”改为“当前项目”即可。其他已有对话需分别通知重新读取规则。

将“已完成／下一步”及轻量规则更新约定配置到 AGENTS.md。适用于使用 AGENTS.md 的 Codex 工作流。版本：0.1.0。

仓库：[StarSure/agent-reply-footer](https://github.com/StarSure/agent-reply-footer)

## 效果

```text
已完成：已生成文档并检查排版
下一步：建议核对文档中的姓名和日期后使用
```

最终答复保留两行，进度更新不必重复；如实报告结果，给出一项具体后续行动，没有必要后续时明确收尾。不为这两行额外调用工具或检查。

## 安装技能

- 本地分享：将 skills/agent-reply-footer 文件夹复制到宿主支持的个人或项目技能目录。当前官方文档列出的个人目录为 ~/.agents/skills，项目目录为 .agents/skills；已有自定义技能目录的用户按实际配置使用。若技能没有出现，重启 Codex。
- GitHub 安装：将本仓库链接发给 Codex，要求使用 `$skill-installer` 安装 `skills/agent-reply-footer`。安装完成后，继续按下方说明启用规则。
- 本仓库提供独立 Skill 源码；面向更广泛的安装和分发，可后续打包成插件。

可直接把下面这句话发给 Codex：

```text
请使用 $skill-installer 从 https://github.com/StarSure/agent-reply-footer 安装 skills/agent-reply-footer。
```

## 启用规则

安装技能后，在对话中发送以下指令之一：

```text
使用 $agent-reply-footer，只在当前对话采用通用收尾规则和更新约定。
```

```text
使用 $agent-reply-footer，将规则安装到当前项目 AGENTS.md，并立即应用于当前对话。
```

```text
使用 $agent-reply-footer，将规则安装到我的全局和当前项目 AGENTS.md，替换旧收尾规则，保留其他内容，并立即应用于当前对话。
```

只有当前对话授权明确时才写入相应范围。只安装技能不会自动改写 AGENTS.md，也不保证所有任务始终自动触发本技能；长期生效由 AGENTS.md 承担。

## 更新与移除

升级 Skill 后，请再调用它更新指定范围的 AGENTS.md。其他已有聊天需分别发送：

```text
请重新读取 <规则文件实际路径> 中的“回复收尾规则”和“规则更新约定”，从本轮起采用新版，替换同一事项的旧要求，保留当前任务进度和其他有效约束。
```

文件不可访问时，也可将规则模板全文粘贴到对话，明确要求采用。跨设备使用需先同步文件。

移除时，可让该技能删除指定 AGENTS.md 中的本套规则；删除 Skill 文件夹本身不会撤销已经写入的规则。

## 文件

- skills/agent-reply-footer/SKILL.md：配置工作流。
- skills/agent-reply-footer/assets/reply-footer-rules.md：通用规则模板。
- skills/agent-reply-footer/agents/openai.yaml：技能界面信息。

本仓库仅包含通用规则，不含作者的项目规则、个人绝对路径或账号配置。

## 官方参考

- [构建与安装技能](https://learn.chatgpt.com/docs/build-skills)
- [AGENTS.md 指令](https://learn.chatgpt.com/docs/agent-configuration/agents-md)

## 许可证

采用 [MIT License](LICENSE)，允许复制、修改、分发和商业使用；请保留许可证与版权声明。
