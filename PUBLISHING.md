# 上架记录

Pro 版布局仓库：<https://github.com/MoruTeaven/xime-layout-romaji-pro>

> 普通版（无数字行）见 <https://github.com/MoruTeaven/xime-layout-romaji>。

## 待提交

| 项目 | 值 |
| --- | --- |
| 目标 PR | [ximeiorg/xime-index](https://github.com/ximeiorg/xime-index) |
| 条目 id | `xime_layout_romaji_pro` |
| 变更文件 | `src/layouts/xime_layout_romaji_pro.yaml`、`layouts/index.yaml` |
| 状态 | 待提交，等待维护者审批 + CI 合并 |

## 提交信息

| 项目 | 值 |
| --- | --- |
| 提交类型 | A. 单文件（纯 yaml 配置，无 themes/fonts 资源） |
| 下载地址 | `https://github.com/MoruTeaven/xime-layout-romaji-pro/releases/download/1.0.0/xime.custom.yaml` |
| sha256 | `cb5ff50f8536e109deb861fc63ac27e15fdee0d48f7c6cafbe12ce4411fc8665` |
| 大小 | 17.1 KB |
| 截图 | 待补（可放 `images/keyboard.png`，固定到 tag `1.0.0`） |
| 许可 | Apache-2.0 |
| appVersion | `>=3.0.0` |

## 合规自查

- 下载地址不可枚举：Release 附件，非分支内容
- 只含 `keyboard` 段与 `metadata`，无 `xime_index` / `color_scheme` / `color_schemes` 等与布局无关的样式
- `requiresSchemes` 留空：布局不绑定特定方案 id，用户需自行安装「罗马字 → 假名」的 Rime 方案
- 未删除任何历史版本

## 后续发版流程

1. 改 `xime.custom.yaml`，提交推送
2. `git tag <version> && git push origin <version>`，workflow 自动建 Release 并上传附件
3. 在 xime-index 的 `src/layouts/xime_layout_romaji_pro.yaml` 顶部新增版本记录，更新 `currentVersion`
4. `python scripts/ci-update.py` 重新生成 `layouts/index.yaml`，提 PR

> 旧版本发布物不要删除，索引需要保留历史版本以供回退。
