# dsh-plugins

[zmengle](https://github.com/zmengle) 给 [DeepSeek Harness](https://github.com/deepseek-ai/deepseek-harness)（`dsh`）写的插件集合。
DeepSeek Harness plugins by zmengle — each one is a standalone, installable `dsh` bundle.

| 插件 | 一句话 | npm | 仓库 |
|---|---|---|---|
| **dsh-plugin-sticky-wall** | 侧栏一块可自由摆放的便签墙（待办/列表、可折叠、回收站、导出导入备份、滚动到顶/到底），给模型 5 个 `sticky_wall_*` 工具 | `1.8.0` | [repo](https://github.com/zmengle/dsh-plugin-sticky-wall) |
| **dsh-plugin-artifacts** | 工作区文件按「产物/过程/记忆/素材」分层管理：多工作区、12 类类型、按年/月/日时间轴、预览/重命名/回收站/归档、可选 COS 同步 | `2.0.0` | [repo](https://github.com/zmengle/dsh-plugin-artifacts) |
| **dsh-plugin-ark-image-gen** | 火山方舟 / 豆包 Seedream 生图：`ark_generate_image` + `ark_image_gen_status` 两个工具 | `0.1.1` | [repo](https://github.com/zmengle/dsh-plugin-ark-image-gen) |

## 安装

```sh
# 从 npm（推荐，一键、免构建）
dsh plugin --profile web add dsh-plugin-sticky-wall
dsh plugin --profile web add dsh-plugin-artifacts
dsh plugin --profile web add dsh-plugin-ark-image-gen
```

也可以从源码装（跑最新 `main`）：

```sh
dsh plugin --profile web add git+https://github.com/zmengle/dsh-plugin-sticky-wall.git
dsh plugin --profile web add git+https://github.com/zmengle/dsh-plugin-artifacts.git
dsh plugin --profile web add git+https://github.com/zmengle/dsh-plugin-ark-image-gen.git
```

装完重启 `dsh web`（桌面端在设置 → 插件里能看到）。每个插件都声明了 `dsh.bundle.patch`，
所以 `dsh plugin add` 认得它们。配置项、截图和踩坑说明在各仓库自己的 README 里。

## 约定

- 每个插件一个独立仓库，`main` 分支 + 语义化版本。
- 模型工具、HTTP 端点都走宿主自己的 seam（`ctx.tools`、`webServer`），不另起进程。
- 不在任何文件里存密钥：只读环境变量或 profile 配置。

## 许可

MIT
