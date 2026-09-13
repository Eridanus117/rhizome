# rhizome

rhizome 是去中心知识库的 authoring / 校验 CLI：知识以 Markdown + frontmatter 分散存在多个普通 Git 仓里，域树由 `INDEX.md` 自发现；rhizome 只管写入契约和提交门禁，不集中存储、不做检索。

- 主要目录：`src/rhizome/`（CLI 与 check、contract、sources、adopt、doctor 等模块）、`tests/`、`mermaid-validator/`（可选的 Node.js Mermaid 校验 sidecar）、`scripts/`（release 构建）。
- 开发与检查：`uv sync --group dev`，`npm ci --prefix mermaid-validator` 后 `uv run pytest -ra`；lint 用 `uvx ruff@0.15.16 check .` 与 `uvx ruff@0.15.16 format --check .`，或 `uv run poe check`。
- 架构、模块与不变量见 `docs/architecture.md`。

## Agent skills

### Issue tracker

Issues 在本仓 GitHub Issues（`Eridanus117/rhizome`）里，`gh` 在仓内自动识别。See `docs/agents/issue-tracker.md`.

### Triage labels

使用默认五个标签：`needs-triage`、`needs-info`、`ready-for-agent`、`ready-for-human`、`wontfix`。See `docs/agents/triage-labels.md`.

### Domain docs

Single-context：根 `CONTEXT.md` + `docs/adr/`（按需生成）。See `docs/agents/domain.md`.
