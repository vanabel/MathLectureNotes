# texbrain-elegantbook

[ElegantBook](https://github.com/ElegantLaTeX/ElegantBook) 中文 + **Adobe OTF** 工程模板，针对 [TeXbrain](https://github.com/vanabel/texbrain) / **BusyTeX**（浏览器 XeLaTeX + BibTeX）配置。

## 快速开始（TeXbrain）

1. 克隆本仓库到本机：
   ```bash
   git clone git@github.com:vanabel/texbrain-elegantbook.git
   cd texbrain-elegantbook
   ```
2. 打开 [TeXbrain](https://tex.vanabel.cn)（或本地 `pnpm dev`）→ **打开文件夹** → 选择 clone 目录。
3. 编译入口：**`main.tex`**（顶栏 Compile → Entry Point 或 Active Tab）。
4. 需要 Git push/pull 时：在 TeXbrain **Git → Remote** 配置 GitHub PAT 与 CORS 代理（见 [TeXbrain 部署文档](https://github.com/vanabel/texbrain/blob/main/docs/zh-CN/deployment.md)）。

`fonts/` 与根目录下的 `bbding` / `adforn` 相关文件已入库，**clone 即可编译**，无需在 NAS 或部署机上安装 TeX Live。

## 仓库内容

| 路径 | 说明 |
| --- | --- |
| `main.tex` | 主文档入口 |
| `elegantbook.cls` | 类文件（含 `./fonts/` 西文字体与 bbding/adforn 回退） |
| `elegantbook-cn-adobe-fonts.tex` | Adobe 中文 OTF 设置 |
| `references.bib` | 示例文献 |
| `fonts/` | TeXGyreTermesX、texgyreheros、Adobe 四套 OTF |
| `setup-fonts.sh` | 在有 TeX Live 的机器上刷新字体/宏包（可选） |

冒烟测试（无 Adobe 要求）：`elegantbook-cn-test.tex`（Fandol，仍依赖 `fonts/` 西文 OTF）。

## 重新生成 fonts/（可选）

在已安装 TeX Live 的机器上：

```bash
./setup-fonts.sh --all
# 或分项：--latin  --latex  --adobe（需 FONTS_SRC 指向 Adobe OTF）
```

## 字体许可

- **TeXGyreTermesX / texgyreheros**：TeX Live / GUST，可再分发。
- **Adobe OTF**：请确认你的授权允许放入 Git 仓库；若需公开仓库且不能分发 Adobe 字体，请改用私有仓库或删除 `fonts/Adobe*.otf` 后本地运行 `./setup-fonts.sh --adobe`。

## 与 TeXbrain 主仓库的关系

本仓库是**用户工程**，不是 TeXbrain 应用本身。TeXbrain 源码：[vanabel/texbrain](https://github.com/vanabel/texbrain)。

示例来源：`texbrain/examples/bibtex-metapost-english-chinese/Elegantbook-cn/`。
