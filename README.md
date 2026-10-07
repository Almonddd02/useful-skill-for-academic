# useful-skill-for-academic

用于 Codex 的科研技能集合，覆盖文献检索、论文阅读与写作、统计审查、科研绘图、同行评审、返修回复和论文汇报。

本仓库整理了 12 个技能包，保留原始 `SKILL.md`、脚本、模板、示例、参考资料与许可声明。

## 技能目录

| 技能 | 用途 |
| --- | --- |
| [academic-research-suite](skills/academic-research-suite/SKILL.md) | 综合研究规划、文献综述、论文写作、评审、研究筛选与实验工作流。 |
| [nature-academic-search](skills/nature-academic-search/README.md) | 多源文献检索、元数据核查、引用转换与他引分析。 |
| [nature-reader](skills/nature-reader/README.md) | 制作包含图表、公式与来源定位的论文中英对照阅读材料。 |
| [nature-writing](skills/nature-writing/README.md) | 根据研究证据组织论文论证、起草章节与准备投稿材料。 |
| [nature-statistics](skills/nature-statistics/README.md) | 审查实验单位、重复数、统计检验、不确定性与统计报告。 |
| [nature-figure](skills/nature-figure/README.md) | 制作和审查多面板论文图、机制图与图形摘要。 |
| [scientific-figure-making](skills/scientific-figure-making/SKILL.md) | 使用 Matplotlib 制作论文图与矢量输出，附设计和 API 参考资料。 |
| [nature-paper2ppt](skills/nature-paper2ppt/README.md) | 将论文整理为包含原始图表和演讲备注的中文 PowerPoint。 |
| [nature-ref-verifier](skills/nature-ref-verifier/README.md) | 交叉核验参考文献字段，生成验证报告并辅助 Zotero 修正。 |
| [nature-reviewer](skills/nature-reviewer/README.md) | 生成独立模拟审稿报告和综合评审意见。 |
| [nature-response](skills/nature-response/README.md) | 起草和审查逐点审稿回复、返修信与修改稿材料。 |
| [nature-shared](skills/nature-shared/README.md) | 供 `nature-*` 技能共同读取的写作、术语与期刊规则资料。 |

## 安装到 Codex

1. 克隆或下载本仓库：

   ```bash
   git clone https://github.com/Almonddd02/useful-skill-for-academic.git
   ```

2. 将 `skills/` 下需要的**完整技能文件夹**复制到 Codex 用户技能目录，保留原文件夹名：

   - Windows：`%USERPROFILE%\.codex\skills`，例如 `C:\Users\Administrator\.codex\skills`。
   - Linux / macOS：`~/.codex/skills`。

   已有同名技能时先备份，再决定是否替换。各 `nature-*` 文件夹应位于同一层级，并一起安装 `nature-shared`，以保留 `../nature-shared/` 引用。`academic-research-suite` 的 `ars/` 和 `codex/` 子目录应完整保留。

3. 重新启动 Codex 或开启新会话后，以 `$技能名` 调用，例如 `$nature-writing`、`$nature-academic-search` 或 `$nature-figure`。`nature-shared` 是共享资料，由其他技能读取。

## 按需准备运行依赖

复制技能文件后，根据实际任务准备对应工具；具体配置以各技能目录中的说明为准。

- **文献检索**：MCP 服务的 Python 依赖位于 [requirements.txt](skills/nature-academic-search/mcp-server/requirements.txt)。配置时替换 `<MCP_SERVER_DIR>` 等路径占位符，并按所用文献源配置环境变量或认证。包内 `install.sh` 面向 Claude MCP 配置，Codex 用户应按自身客户端配置 MCP。
- **科研绘图**：Python 绘图按需使用 Matplotlib、NumPy、Pandas 或 SciPy；PDF 审计依赖 [nature-figure/requirements.txt](skills/nature-figure/requirements.txt) 中的 PyMuPDF。R 绘图和 AI 示意图按对应参考文档准备工具与服务配置。
- **论文转 PPT**：按需安装 PyMuPDF、Pillow 和 python-pptx；LibreOffice 可用于预览。
- **综合研究套件**：优先阅读 [Codex 适配说明](skills/academic-research-suite/codex/README.md)。开发与验证依赖见 [requirements-dev.txt](skills/academic-research-suite/ars/requirements-dev.txt)，文档导出工具按任务选择。

参考文档中的示例输入、输出路径需要替换为自己的路径。API 密钥应通过本机配置或环境变量提供。

## 来源与许可

技能文件来自用户提供的 12 个 ZIP 包，导入记录及压缩包 SHA-256 见 [import-manifest.json](docs/import-manifest.json)。

- `academic-research-suite` 的上游来源、版本和提交记录见 [manifest.json](skills/academic-research-suite/manifest.json)；保留了原作者 Cheng-I Wu 的 [CC BY-NC 4.0 许可](skills/academic-research-suite/ars/LICENSE)、NOTICE 与第三方说明。
- `nature-figure` 中 `figures4papers` 参考素材的来源与许可情况见 [THIRD_PARTY_NOTICES.md](skills/nature-figure/assets/figures4papers/THIRD_PARTY_NOTICES.md)。
- 各技能及第三方素材适用其原有许可与来源说明；本仓库未新增覆盖所有内容的统一许可证。
