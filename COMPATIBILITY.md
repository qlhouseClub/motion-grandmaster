# 跨平台兼容指南

`SKILL.md`、`references/`、`assets/` 和 `agents/openai.yaml` 是唯一技能源。`scripts/build_compat.py` 生成 TRAE、OpenAI Plugin、扣子和便携包到 `dist/`。

| 平台 | 兼容级别 | 形态 |
|---|---|---|
| Codex / ChatGPT 桌面端 | 原生 | Agent Skill |
| ChatGPT Work | 原生分发 | OpenAI Plugin 与本地 Marketplace |
| TRAE Work / SOLO / IDE | 原生打包 | ZIP 或完整技能目录 |
| Hermes Agent | 原生 | `SKILL.md` + 引用 + 模板 |
| OpenClaw | 原生 | Git 或本地目录安装 |
| 扣子 / Coze | 转换兼容 | 系统提示词 + 知识库 |

## 构建

```powershell
python .\scripts\build_compat.py --platform all
```

可选平台：`trae`、`openai`、`coze`、`portable`。

## 平台边界

- 专业规则不为平台复制多份；所有适配均从同一技能源构建。
- 扣子没有原生 Agent Skill 目录时，使用行为桥接与知识检索。
- 没有浏览器、视频、音频、渲染、代码或性能工具时，只能交付动效方向与规范，不得声称已完成实时趋势研究、动画播放检查或性能验证。
- 视频录制不能证明交互可中断、焦点正确或真实运行性能。
- 部分 TRAE 版本可能丢失 ZIP 内引用目录，导入后必须检查，必要时复制完整文件夹。
- 私有仓库安装需要凭据；公开仓库前清除客户资产、字体、音频、视频、Token、账号和无权分发内容。

## 维护

1. 专业能力：`SKILL.md`、`references/`
2. 交付模板：`assets/`
3. OpenAI 展示：`agents/openai.yaml`
4. 扣子桥接：`platforms/coze/agent-prompt.md`
5. 版本与仓库：`platforms/manifest.json`
6. 不手工编辑或提交 `dist/`

## 官方依据

- [OpenAI Build skills](https://learn.chatgpt.com/docs/build-skills)
- [OpenAI Build plugins](https://learn.chatgpt.com/docs/build-plugins)
- [Hermes Agent Skills](https://github.com/NousResearch/hermes-agent/blob/main/website/docs/user-guide/features/skills.md)
- [OpenClaw Skills](https://github.com/openclaw/openclaw/blob/main/docs/tools/skills.md)
- [Coze Studio](https://github.com/coze-dev/coze-studio)
