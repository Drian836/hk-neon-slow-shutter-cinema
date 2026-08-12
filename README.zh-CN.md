# 香港都市霓虹慢快门电影 Visual Skill

[English](README.md) · [安装与下载](INSTALL.md)

这是一个 Codex Visual Skill，用于生成、转译、分析带有 1980 年代末至 2000 年前后香港都市生活气息的电影画面，也可在明确请求时设计香港电影海报。它会把简短自然语言、人物照片、电影截图或海报参考，路由为可执行的作品视觉家族、场景、时间、镜头关系、光色、构图、胶片或印刷再现系统。

该 Skill 的目标是通过可执行的香港都市电影视觉规则，生成具有统一家族感、但不会机械重复的图片。核心是：

- scene grammar（场景语法）；
- visual-family routing（作品视觉家族路由）；
- relative-clock grammar（两个相对时钟与运动时间语法）；
- camera-subject relation（镜头—人物—空间关系）；
- lighting grammar（实际光源与颜色语法）；
- composition grammar（构图与空间语法）；
- character preservation（人物与输入图保护）；
- film reproduction（不完美彩色胶片再现）；
- variation 与 actual-raster quality gate（变化与实际成图质量门）。
- poster routing（电影帧证据与海报设计证据分流）。

它不是一段固定 Prompt，也不依赖导演姓名才能工作。

## 适合的输入

- 简短场景：“一个女生凌晨站在街角等人。”
- 动作或情绪：“一个男人穿过拥挤人群，周围都很快，他感觉时间停住了。”
- 必须保持可辨识身份的人像、宠物、产品或物件照片。
- 只用于学习拖影、颜色、光线、构图或质感的电影截图和参考图。
- “分析这些截图为什么有香港电影感”一类分析请求。
- 只要最终 Prompt，或需要同系列多张变化的请求。

## 视觉特点

固定家族特征包括：生活化香港都市空间、人物嵌入真实环境、选择性方向拖影、明确前中后景、实际光源混色、情绪距离，以及不完美胶片再现。

“慢快门”不会被理解为整张平均模糊。Skill 会先区分连续慢门、传统慢动作感和步印/抽帧时间，再明确指定：

- 哪些信息稳定并保持可读；
- 哪些人物、车辆或环境移动；
- 运动方向与强度；
- 哪些边缘出现轻微时间残影；
- 哪些灯光轨迹必须依附于真实移动光源。
- 镜头是跟随主体、锁定主体、随车移动还是隔着门框观察；
- 哪两个空间平面处于不同的表观时钟；
- 步印要求的断续边缘、间隔、局部残影和分段灯迹。

系统不会把不同作品压成同一种青绿红霓虹滤镜。它按内容选择一个主要视觉家族：潮湿室内漂移、都市时间流、夜间近广角疏离、克制走廊记忆、漂泊与逼仄亲密；电影名称只用于理解意图，最终 Prompt 仍由可见像素行为构成。

特别强调：**香港夜景不等于赛博朋克。** Anti-Identity 会阻止未来城市、干净紫蓝 RGB 霓虹、彩虹灯、游戏美术、合成雾、无菌现代商场、商业美妆人像、棚拍灯、现代光滑广告和完美数码锐度等漂移。

## 安装

### 下载源码

- 版本化下载：进入 [Releases](https://github.com/Drian836/hk-neon-slow-shutter-cinema/releases)，选择 `v0.3.0`，再下载 **Source code (zip)** 或 **Source code (tar.gz)**；解压后将顶层目录重命名为 `hk-neon-slow-shutter-cinema` 再安装；
- v0.3.0 ZIP 直链：<https://github.com/Drian836/hk-neon-slow-shutter-cinema/archive/refs/tags/v0.3.0.zip>；
- GitHub 源码包：在仓库页面选择 **Code → Download ZIP**；
- Git 克隆：

```bash
git clone https://github.com/Drian836/hk-neon-slow-shutter-cinema.git
```

Windows、macOS/Linux、更新、验证与卸载方法见 [`INSTALL.md`](INSTALL.md)。

把完整目录复制到 Codex 的 Skills 目录：

```text
~/.codex/skills/hk-neon-slow-shutter-cinema/
```

不需要数据库、RAG、Obsidian、外部 API、Python 运行脚本或第三方依赖。如果新安装后当前任务没有立即显示，可重启 Codex 或新建任务。

## 使用

可显式调用：

```text
使用 $hk-neon-slow-shutter-cinema 做一个女生凌晨站在香港街角等人的画面。
```

当请求出现“港风电影感”“90年代香港”“香港慢门”“时间拖影”或相关参考图分析时，也可以自动匹配。

### 六种模式

- **Generate Mode：**理解内容、选择视觉策略、编译 Prompt、生成图片、检查实际 raster，并在必要时最多定向返修一次。
- **Photo Input Mode：**给输入图分配角色和保护等级，把真实图片传入生成，并检查人物身份、产品几何或服装等 invariants。
- **Reference Analysis Mode：**检查真实参考图，严格区分可复用风格语法与单张样本残留。
- **Prompt-only Mode：**只返回可直接用于图片模型的三至四段自然语言 Prompt，不虚构生成或成图检查。
- **Analyze + Generate Mode：**从参考图提取指定规律，再用全新人物和构图生成，不复制原镜头。
- **Poster Mode：**把电影帧/照片与官方海报、二创海报分别分类，再组合全新的图像层、标题层和印刷层；不复制演员、原片帧、标题字标、Logo、奖项或完整版式。

## 完整工作流

```text
Input
→ Request Routing
→ Parse Intent
→ Select One Primary Visual Family
→ Scene / Emotional Interpretation
→ Select Relative Clocks, Camera Relation, Space, Light, and Film Strategy
→ Select Variation Recipe
→ Compile Renderable Prompt
→ Generate
→ Inspect Actual Raster
→ Quality Gate
→ 最多一次定向返修
→ 返回图片、Prompt、Recipe 与检查说明
```

## 目录结构

```text
hk-neon-slow-shutter-cinema/
├── SKILL.md                       # 身份、路由、总流程、输入图角色、返修与输出协议
├── README.md
├── README.zh-CN.md
├── agents/openai.yaml            # Codex UI 展示信息与默认调用语句
├── evals/evals.json              # 路由、推理、编译、保护与 QA 测试
├── examples/                     # 三条不含版权剧照的完整示例
└── references/
    ├── style-system.md           # 固定家族、变量、情绪、空间、胶片与 Anti-Identity
    ├── visual-families.md        # 五类作品视觉家族、意图映射和跨家族混合规则
    ├── poster-system.md          # 海报分类、版式、字体、印刷和海报 QA
    ├── scene-system.md           # 生活化空间语法
    ├── motion-system.md          # 两个时钟、镜头关系、方向、断续时间与 8 类 recipe
    ├── lighting-color-system.md  # 实际光源逻辑和受控 palette families
    ├── composition-system.md     # 12 类构图与前中后景关系
    ├── character-system.md       # 人物、物件和 Photo Input 保护
    ├── variation-engine.md       # 变化轴、批量约束与 recipe 记录
    ├── prompt-compiler.md        # 12 字段到三至四段自然语言 Prompt
    ├── reference-analysis.md     # 证据、固定/变量系统与样本残留分离
    └── quality-gate.md           # Anti-Grade、Explicit-Time、100 分验收与有界返修
```

`SKILL.md` 只保留 Router 和工作流内核；专业知识按需要逐步加载。示例不捆绑电影剧照，Evals 覆盖生成、输入照片、参考图分析、Prompt-only、批量变化和反赛博朋克控制。

## 示例 Recipe

```text
[Urban Temporal Flux / street corner / pre-dawn / one woman waiting / Step-Printed Drift, crowd at a faster clock / camera locked near subject / Foreground Occlusion / Green Fluorescent + Amber Tungsten / moderate-wide environmental intimacy / coarse color-film grain / restless longing]
```

完整 Prompt 与检查重点见 `examples/waiting-at-street-corner.md`。

## 限制

- 单张生成图可以模拟 frame echo 和 step-print-like 时间断续，但不能等同于真实多帧光学工艺。
- 当前图片模型更稳定地产生“主体清楚、环境连续慢门”，对真正断续的步印残影仍可能不服从；显式步印请求必须通过单独硬门，不得用色调代替。
- 图片模型仍可能发生身份、手部、文字、车辆、年代细节或运动因果错误；最多一次有界返修只能降低风险，不能完全消除。
- 在线截图、不同修复版和裁切版本会改变色相、反差、颗粒与画幅。因此参考分析必须分开记录 Observed、Inferred、Reported 和 transfer uncertainty。
- 本 Skill 生成抽象视觉语法，不复制演员、具体电影镜头、受保护角色、字幕、Logo 或原构图。
- 年代真实性以可信方向为主，不等于档案级复原。若必须准确到具体年份、线路、品牌、制服或车型，应提供证据并要求单独核验。

## 许可证状态

当前尚未选择开源许可证。公开仓库可以查看和下载，但在仓库所有者添加许可证前，不额外授予法律默认范围之外的复制、修改或再分发权利。
