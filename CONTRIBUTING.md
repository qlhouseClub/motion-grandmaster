# 贡献指南

专业能力修改 `SKILL.md` 或 `references/`；模板修改 `assets/`；平台展示和适配修改 `agents/openai.yaml` 与 `platforms/`。不要手工编辑或提交 `dist/`。

贡献必须：

1. 从用途、Motion Thesis 和时间构图出发，不从动画库或趋势名出发。
2. 保持既有 Motion Token、组件行为和品牌规范默认只读。
3. 同时说明 reduced motion、感官替代、性能与降级。
4. 高审美方案说明参考机制、特异性、克制和生产证明。
5. 外部材料核验代码许可与媒体/字体/音乐/品牌权利。
6. 不模仿在世创作者、工作室或品牌的可识别动态签名。
7. 运行 `python scripts/build_compat.py --platform all`、技能校验和 `git diff --check`。

安全问题按 [SECURITY.md](SECURITY.md) 私密报告。
