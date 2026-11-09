# 折腾派公众号排版

一个适用于 Codex 的微信公众号排版 skill，面向中文观点文章与随笔。保留原文，用红白配色、章节编号和留白组织内容，生成可复制到公众号编辑器的 HTML。

## 版式

- 正文以常规字重为主，只突出少量完整句子，通常为 3–5 句，短文更少。
- 不使用关键词下划线、零碎词组加粗或词组色块。
- 不添加导读卡片、章节底线和横向分割线。
- 正文 15px，行高 1.8，容器最大宽度 677px。
- 支持文末作者简介原图，完整显示、按比例缩放。

## 安装

克隆到 Codex 的个人 skills 目录。例如在 Windows PowerShell 中：

```powershell
git clone https://github.com/zcx28/zhetengpai-wechat-layout.git "$env:USERPROFILE\.codex\skills\zhetengpai-wechat-layout"
```

如果使用了自定义 `CODEX_HOME`，安装到该目录下的 `skills/zhetengpai-wechat-layout`。

安装后，在下一次对话中使用：

> 使用 $zhetengpai-wechat-layout 排版下面这篇公众号文章。

也可以说“按折腾派排版”，并提供文章。

## 输出

skill 提供独立正文 HTML，以及带“复制到公众号”按钮的预览页。打开预览，点击复制，再到公众号编辑器粘贴。

附带的工具只依赖 Python 标准库：

```text
python scripts/validate_gzh_html.py <正文.html>
python scripts/wrap_preview.py <正文.html>
```

简介原图未包含在仓库中。需要时将原图保存为 `assets/author-intro.png`；没有原图时，正文仍可正常排版。离线预览与复制检查不等于已验证公众号编辑器中的最终效果。

详细排版规则见 [SKILL.md](SKILL.md)，组件见 [references/components.md](references/components.md)。

## 来源与许可

本项目的组件、校验器和预览外壳基于 [isjiamu/gzh-design-skill](https://github.com/isjiamu/gzh-design-skill)，按少量整句强调的个人版式调整。

依照上游许可，以 **GNU Affero General Public License v3.0 or later** 开源，保留上游版权与署名。完整许可见 [LICENSE](LICENSE)。
