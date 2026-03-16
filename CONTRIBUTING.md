# Contributing

本仓库用于统一管理自研 Agent Skills。

## 新增 Skill 的目录规范

每个 skill 必须独立放在：

```text
skills/{skill-name}/
```

推荐最小结构：

```text
skills/{skill-name}/
  SKILL.md
  README.md
  references/
  scripts/
  config.template.json
```

## 命名规范

- skill 名称统一使用 `kebab-case`
- 一个 skill 一个目录
- 不要把 skill 的私有脚本、参考资料、配置模板放到仓库顶层

## 文件职责

- `SKILL.md`：给 Agent / Runtime 读取的核心技能说明
- `README.md`：给人阅读的说明文档
- `references/`：背景资料、接口说明、设计笔记
- `scripts/`：脚本、依赖、辅助程序
- `config.template.json`：配置模板，不包含真实凭据

## 安全约定

禁止提交：

- 真实账号密码
- token / secret / cookie
- `config.local.json`
- runtime 输出文件
- 临时抓取结果
- 本地归档数据

## 新增 Skill 的建议流程

1. 复制一个现有 skill 目录作为骨架
2. 修改 `SKILL.md`
3. 修改 `README.md`
4. 把该 skill 私有脚本放进 `scripts/`
5. 把参考资料放进 `references/`
6. 检查 `.gitignore`，确保不会提交本地配置和运行产物

## 提交前检查

提交前至少确认：

- 仓库顶层没有残留 skill 私有文件
- 文档路径与当前仓库结构一致
- 脚本中的默认路径与仓库结构一致
- 没有敏感信息进入 Git 历史
