# Obsidian Git 插件

> **关于本仓库**
>
> 本仓库是 [Vinzent03/obsidian-git](https://github.com/Vinzent03/obsidian-git) 的**中文汉化 fork**，仅对 `README.md` 进行了中文翻译，便于中文用户阅读。
> 原版英文 README 见 [README.en.md](./README.en.md)。
> 如需同步上游更新，请在原仓库发起 issue 或 PR。
>
> 上游原项目地址：<https://github.com/Vinzent03/obsidian-git>
>
> 原始许可证、CHANGELOG、源码、CI 配置等全部继承自上游，未做任何修改。

一个为 [Obsidian.md](https://obsidian.md) 打造的功能强大的社区插件，将 Git 集成直接带到你的 Vault 中。在 Obsidian 内部即可自动提交、拉取、推送并查看你的更改。

## 📚 文档

所有的安装步骤（包括移动端）、常见问题、实用技巧以及高级配置，都收录在 📖 [完整文档](https://publish.obsidian.md/git-doc) 中。

> 移动端用户请注意：该插件在移动端**非常不稳定 ⚠️**！请查阅下方专门的 [移动端支持](#-移动端支持-️-实验性) 一节。

## 核心功能

- 🔁 **自动提交并同步**（commit、pull、push），按设定周期执行。
- 📥 **Obsidian 启动时自动拉取**
- 📂 **子模块（Submodule）支持**，便于管理多个仓库（仅桌面端，需手动开启）
- 🔧 **源码控制视图**，可暂存/取消暂存、提交、对比文件 — 通过 `打开源码控制视图` 命令打开。
- 📜 **历史视图**，浏览提交日志和变更文件 — 通过 `打开历史视图` 命令打开。
- 🔍 **差异视图**，查看单个文件的变更 — 通过 `打开差异视图` 命令打开。
- 📝 **编辑器内变更标记**，直观展示新增、修改、删除的行/块（仅桌面端）。
- GitHub 集成，可在浏览器中打开文件及历史记录

> 如需更详细的文件历史记录，建议搭配 [Version History Diff](obsidian://show-plugin?id=obsidian-version-history-diff) 插件使用。

## 界面预览

### 🔧 源码控制视图

在 Obsidian 内部直接管理文件变更，例如单独暂存/取消暂存文件并提交。

![源码控制视图](https://raw.githubusercontent.com/Vinzent03/obsidian-git/master/images/source-view.png)

### 📜 历史视图

展示仓库的提交历史。可以查看提交信息、作者、日期以及变更的文件。如截图所示，作者和日期默认是关闭的，可以在设置中开启。

![历史视图](https://raw.githubusercontent.com/Vinzent03/obsidian-git/master/images/history-view.png)

### 🔍 差异视图

使用清晰简洁的差异查看器对比不同版本之间的变化。
可以从源码控制视图中打开，也可以通过 `打开差异视图` 命令打开。

![差异视图](https://raw.githubusercontent.com/Vinzent03/obsidian-git/master/images/diff-view.png)

### 📝 编辑器内变更标记

直接在编辑器中查看逐行的变更，并显示新增、修改、删除的行/块标记。你可以从这些标记处直接暂存或撤销对应变更。还提供在变更块之间跳转以及暂存/撤销光标处变更块的命令。需要先在插件设置中开启。

![变更标记](https://raw.githubusercontent.com/Vinzent03/obsidian-git/master/images/signs.png)

## 可用命令

> 这里只是部分最常用的命令，并非完整列表。完整列表请查看 Obsidian 中的命令面板。

- 🔄 变更
  - `列出变更文件`：在弹窗中列出所有变更
  - `打开差异视图`：为当前文件打开差异视图
  - `暂存当前文件`
  - `取消暂存当前文件`
  - `丢弃所有变更`：丢弃仓库中的所有变更
- ✅ 提交
  - `提交`：如果存在已暂存的文件，则只提交已暂存的文件
  - `使用指定消息提交`：同上，但可使用自定义提交信息
  - `提交所有变更`：提交所有变更但不推送
  - `使用指定消息提交所有变更`：同上，但可使用自定义提交信息
- 🔀 提交并同步
  - `提交并同步`：使用默认设置时，会提交所有变更、拉取并推送
  - `使用指定消息提交并同步`：同上，但可使用自定义提交信息
  - `提交并同步后关闭`：与 `提交并同步` 相同，但如果在桌面端运行，会关闭 Obsidian 窗口。移动端不会退出 Obsidian 应用。
- 🌐 远程
  - `推送`、`拉取`
  - `编辑远程仓库`：添加新的远程仓库或编辑已有远程仓库
  - `删除远程仓库`
  - `克隆已有远程仓库`：打开对话框，提示输入 URL 和认证信息以克隆远程仓库
  - `在 GitHub 上打开文件`：在浏览器中打开当前文件在 GitHub 上的文件视图。注意：仅桌面端可用
  - `在 GitHub 上打开文件历史`：在浏览器中打开当前文件在 GitHub 上的历史记录。注意：仅桌面端可用
- 🏠 管理本地仓库
  - `初始化新仓库`
  - `创建新分支`
  - `删除分支`
  - `⚠️ 慎用：删除仓库`
- 🧪 杂项
  - `打开源码控制视图`：打开侧边栏面板，显示 [源码控制视图](#-源码控制视图)
  - `打开历史视图`：打开侧边栏面板，显示 [历史视图](#-历史视图)
  - `编辑 .gitignore`
  - `添加文件到 .gitignore`：将当前文件加入 `.gitignore`

## 💻 桌面端说明

### 🔐 身份认证

部分 Git 服务在使用 HTTPS/SSH 时可能需要进一步配置。请参考 [身份认证指南](https://publish.obsidian.md/git-doc/Authentication)。

### Linux 上的 Obsidian

- ⚠️ 不支持 Snap，因为其沙箱限制。
- ⚠️ 不推荐使用 Flatpak，因为它无法访问所有系统文件。他们正在积极修复诸多问题，但目前仍存在不少问题，尤其在较复杂的配置下。
- ✅ 请改用 AppImage，或通过系统包管理器进行完整权限安装（[Linux 安装指南](https://publish.obsidian.md/git-doc/Installation#Linux)）

## 📱 移动端支持（⚠️ 实验性）

移动端的 Git 实现**非常不稳定**！不推荐在移动端使用本插件，建议尝试其他同步服务。

其中一个替代方案是 [GitSync](https://github.com/ViscousPot/GitSync)，它在 Android 和 iOS 上都可用。它与本插件没有关联，但对移动端用户来说可能是更合适的选择。设置教程可参见 [这里](https://viscouspotenti.al/posts/gitsync-all-devices-tutorial)。

> 🧪 移动端能运行本 Git 插件得益于 [isomorphic-git](https://isomorphic-git.org/) —— 一个基于 JavaScript 的 Git 重新实现 —— 但它存在严重的限制和问题。Obsidian 插件在 Android 或 iOS 上无法调用原生 Git 实现。

### ❌ 移动端功能限制

- 不支持 **SSH 认证**（[isomorphic-git 问题](https://github.com/isomorphic-git/isomorphic-git/issues/231)）
- 由于内存限制，仓库体积受限
- 不支持 rebase 合并策略
- 不支持子模块

### ⚠️ 性能注意事项

> [!caution]
> 取决于你的设备和可用内存，Obsidian 可能会出现以下情况：
>
> - 在 clone/pull 时崩溃
> - 出现缓冲区溢出错误
> - 长时间卡住无响应。
>
> 这是因为移动端底层的 Git 实现效率不高造成的，我不知道如何修复。如果你遇到了这种情况，那很遗憾这个插件对你来说确实不可用。所以在 issue 下评论或新开 issue 也无济于事，抱歉。

### 移动端使用建议

如果你的仓库/Vault 比较大，建议只暂存单独的文件，并只提交已暂存的文件。

## 🙋 联系与致谢

- 行级编辑功能（Line Authoring）由 [GollyTicker](https://github.com/GollyTicker) 开发，如有相关问题可以直接联系她。
- 本插件最初由 [denolehov](https://github.com/denolehov) 开发。自 2021 年 3 月起，由 [Vinzent03](https://github.com/Vinzent03)（也就是我）接手开发。这也是为什么 GitHub 仓库在 2024 年 7 月迁移到了他的账号下。
- 如果你有任何反馈或问题，欢迎通过 GitHub issues 与他联系。

## ☕ 支持原作者

如果你觉得这个插件有用，并希望支持原作者的持续开发，可以在 Ko-fi 上支持 Vinzent03。

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/F1F195IQ5)
