# 靛影下山 · Indigo Descent

> 把任意一张图片，重绘成《下山》里那片靛蓝的纸本梦境。

<img width="565" height="421" alt="image" src="https://github.com/user-attachments/assets/52ac8df7-b0a0-4d55-8390-c815a2910dce" />


![Text License](https://img.shields.io/badge/text-MIT-17384A)
![Asset License](https://img.shields.io/badge/stills-CC%20BY--NC%204.0-A33A2C)
![Format](https://img.shields.io/badge/format-Agent%20Skill-B98A4E)
![Input](https://img.shields.io/badge/input-any%20image-4F6B70)

**靛影下山**是一个可安装的视觉 Skill：给它一张照片、插画、宠物、产品图或建筑图，它会把画面重绘成“暖纸底、靛蓝结构、朱砂点睛、巨物与微人”的东方岩彩电影插画；也可以继续把这张图变成 5–8 秒的图生视频。

它提炼自交互作品《下山》的四段影像，但**不要求输入图里有马，也不复制原片地标**。马只是原作的锚点；可迁移的是纸、色、尺度、留白与运动。

---

## 它做什么

- **任意图片二创**：人像、宠物、产品、建筑、风景、街拍、时装、角色。
- **风格转译**：不是加蓝色滤镜，而是重绘材质、空间、色彩比例与尺度关系。
- **图生视频**：给首帧、镜头运动、微动作、稳定性约束与负向词。
- **提示词包**：8 份可直接复制的 `.txt`（中英双语），适配 Midjourney / SD / ComfyUI / 即梦 / 可灵 / 通义万相。
- **验收标准**：缩略图测试、色比测试、主体保真、材质检查、视频稳定性检查。

## 它不做什么

- 不训练模型、不包含权重、不是 LoRA。
- 不保证“一键同款”；它给的是可执行的创作规则与提示词。
- 不把参考帧说成生成结果。
- 不适用于青绿水墨田园游历——那是另一个 skill：`ink-wash-journey`。
- 不适用于写实摄影、赛博霓虹、日式赛璐璐。

---

## 与《贵州兴义》的关系

<img width="565" height="286" alt="image" src="https://github.com/user-attachments/assets/3217e601-0a8f-4381-b902-83536e14a619" />


有两个相关但不同的作品：

- **《贵州兴义》**：青绿 + 水墨 + 田园游历，约 40.4 秒；已由另一个独立的 skill `ink-wash-journey` 覆盖（不在本仓库内）。
- **《下山》**：靛蓝 + 朱砂 + 纸本重彩 + 巨物微人，四段影像；**本 skill 聚焦这个**。

它们共享纸底、留白、横向层叠、慢镜头与微缩比例，但颜色结构、题材和运动不同。不要用同一条提示词把两者混在一起。

如果要做一组“贵州”视觉：用 `indigo-descent` 做人物、产品、史诗主视觉；用 `ink-wash-journey` 做风景、田园的呼吸段；两者保持同一纸纹、颗粒与输出尺寸，系列感来自这些共同底层，而不是把颜色调成一样。

---

## 30 秒上手

把下面这段和你的图片一起发给 agent：

```text
使用 indigo-descent，把这张图转成《下山》的东方岩彩电影插画。
保留：[脸型/发型/眼镜；或宠物的毛色与花纹；或产品外形与 logo 位置]。
模式 A，16:9，主体放在画面右侧，左侧留白；加一个 5% 高的深色剪影作为比例尺。
不要加马，不要生成文字。
```

只想复制提示词？直接拿这两段：

```text
暖象牙色旧纸/旧绢上的东方岩彩电影插画。以靛蓝、普鲁士蓝和墨蓝承担结构；朱砂红只作少量点睛；赭金与旧金用于日轮、金箔和干草。大色块平涂，干笔毛边与残缺边缘，内部细刻线、涡卷与植物纹样，矿物颗粒，雾层与大面积留白，低地平线，横向层叠空间，哑光无高光。

同一个 [主体]，保持 [2–3 个识别特征]。[姿态与朝向]。主体占画面 45–65%，略偏右；一个 3–8% 高的深色剪影人物站在下方作为比例尺；背景只保留一层远山、一层雾和一个赭金圆盘；左侧留出纸白。

负向：写实摄影，3D 渲染，塑料高光，HDR，镜头光晕，赛博霓虹，日式赛璐璐，随机文字，水印，多余肢体，脸崩，装饰吞没主体。
```

---

## 预览

<img width="564" height="407" alt="image" src="https://github.com/user-attachments/assets/71b52ff9-bbff-4205-aa32-b742e30a973e" />


色板与建议比例：

![Uploading image.png…]()



---

## 安装

### Claude Code

```bash
git clone <your-repo-url> ~/.claude/skills/indigo-descent
```

把 `<your-repo-url>` 换成你的 GitHub 仓库地址。

项目内使用：

```bash
mkdir -p .claude/skills
cp -R indigo-descent .claude/skills/
```

确保 `SKILL.md` 位于技能目录根部：

```text
.claude/skills/indigo-descent/
├── SKILL.md
├── references/
├── prompts/
└── assets/
```

### Codex / 其他 Agent

把整个目录放进你的 agent 的 skills 目录（常见为 `~/.codex/skills/`，以你的版本为准），或在项目里直接引用：

```text
请阅读 indigo-descent/SKILL.md，并按 references/image-transfer.md 的流程处理我上传的图片。
```

### ChatGPT / Custom GPT / Project

- 把 `SKILL.md` 贴进 Instructions。
- 把 `references/*.md` 与 `prompts/*.txt` 作为知识文件上传。
- 图片二创仍需外部的图像生成工具；本 skill 负责读图、定构图、写提示词与验收。

### 只用提示词

不需要安装。直接打开：

- `prompts/style-lock.zh.txt` / `style-lock.en.txt`
- `prompts/image-transfer.zh.txt` / `image-transfer.en.txt`
- `prompts/video.zh.txt` / `video.en.txt`
- `prompts/negative.zh.txt` / `negative.en.txt`

---

## 用法

### 1. 任意图片二创

```text
用 indigo-descent 把这张照片转成《下山》风格：
保留我的脸、短发和圆框眼镜；衣服改成靛蓝立领长袍，朱砂只放在唇色和腰带；
半身，右侧构图，左侧留白；背景一层远山和一个赭金圆盘；左下角加一个 5% 高的小人。
不要加马，不要文字，4:5。
```

Agent 应该先读图、列出“绝不能丢的三件事”，再选模式与构图，最后给提示词与参数；如果它有图像工具，才实际生成。

### 2. 图生视频

```text
用这张已经风格化的图做 5 秒图生视频：
镜头缓慢推近，人物几乎不动，只有呼吸、发丝和衣摆；雾从右侧漫入；远山和圆盘保持稳定。
运动幅度 2/10，24fps，不要镜头翻滚、不要变形、不要闪烁。
```

先有风格化首帧，再做图生视频。不要拿原始照片直接跑视频。

### 3. 只要提示词

打开 `prompts/`，按“风格锁 → 主体锁 → 构图 → 负向”拼。不要每条都重新发明风格。

### 4. 做一组同风格图

- 复用同一段风格锁与同一张纸纹。
- 只改主体、构图、色比三个变量之一。
- 同一系列固定种子；视频固定首帧与尾帧。
- 一致性来自重复，不来自堆形容词。

---

## 程序化使用

`style.json` 提供色板、面积比例、模式、默认旋钮与视频默认参数，方便在自己的应用、脚本或工作流里读取。提示词正文仍以 `prompts/*.txt` 为准，避免两份文案不同步。

```json
{
  "name": "indigo-descent",
  "palette": { "paper": "#E7DDC8", "indigo": "#17384A", "vermilion": "#A33A2C" },
  "ratios": { "paper_and_sand": 0.5, "indigo_and_ink": 0.28, "vermilion": 0.05 },
  "defaults": { "mode": "SILENT", "aspect_ratio": "16:9", "restraint": 70 }
}
```

---

## 风格 DNA

| 维度 | 规则 |
| --- | --- |
| 纸 | 暖象牙/旧绢，纤维、水渍、颜料颗粒；留白 ≥ 1/3 |
| 色 | 靛蓝/墨蓝承担结构；朱砂 5–8% 做锚点；赭金做日轮与金箔；最暗墨蓝，最亮骨白 |
| 形 | 先剪影后细节；干笔毛边、残缺边缘；内部细刻线、涡卷、植物纹 |
| 人 | 次要人物是深色剪影，不画五官；主要人物只留轮廓、发型、一件标志物 |
| 尺度 | 主体放大 1.5–4 倍；一个 3–8% 高的微人做比例尺 |
| 空间 | 前景压边 → 中景主体 → 远山/建筑 → 纸天；低地平线，横向层叠 |
| 光 | 漫射、哑光、无高光、无镜头光晕、无写实体积 |
| 动 | 一条镜头一个主运动；雾、飘带、鬃毛、衣摆做二级运动 |

三种模式：

- **A 静默山水**：人像、宠物、产品、建筑、风景的默认。
- **B 市集群像**：街拍、群像、活动、旅行。
- **C 重彩图鉴**：角色、时装、专辑封面、潮流海报。

完整规则见 [风格 DNA](references/style-dna.md)，图片流程见 [任意图片的二创流程](references/image-transfer.md)，视频见 [运动与视频规则](references/video-motion.md)。

---

## 目录

```text
indigo-descent/
├── SKILL.md                     # 技能入口：何时用、怎么执行、输出什么
├── README.md
├── LICENSE                      # 文本/提示词：MIT
├── LICENSE-ASSETS               # 预览静帧/封面/GIF：CC BY-NC 4.0；色板/图标：MIT
├── CITATION.cff
├── style.json                   # 机器可读的色板、比例、模式与默认参数
├── agents/
│   └── openai.yaml              # Codex / ChatGPT 兼容描述
├── references/
│   ├── style-dna.md             # 色板、材质、构图、风格旋钮、反风格
│   ├── image-transfer.md        # 任意图片二创：保真、遮罩、ControlNet、后期
│   ├── video-motion.md          # 镜头、时长、图生视频、转场、稳定性
│   ├── prompt-library.md        # 中英模板、平台写法、完整示例
│   └── quality-check.md         # 五项硬检查、评分表、交付话术
├── prompts/
│   ├── style-lock.zh.txt
│   ├── style-lock.en.txt
│   ├── image-transfer.zh.txt
│   ├── image-transfer.en.txt
│   ├── video.zh.txt
│   ├── video.en.txt
│   ├── negative.zh.txt
│   └── negative.en.txt
├── examples/
│   ├── portrait.md
│   ├── pet.md
│   ├── product.md
│   └── landscape.md
└── assets/
    ├── README.md                  # 资产来源与授权
    ├── cover.jpg
    ├── contact-sheet.jpg
    ├── lineage.jpg
    ├── palette.png
    ├── motion-preview.gif
    ├── icon.png
    └── still-01.jpg … still-04.jpg
```

---

## 设计原则

1. **先保真，再风格。** 主体认不出，风格再对也是失败。
2. **色比不是调色。** 靛蓝是结构，朱砂是标点，赭金是时间；不是“蓝红撞色”。
3. **留白是主体。** 没有纸白与雾，就只剩一张蓝色插画。
4. **微人是尺度。** 巨物感来自旁边那个很小的人，不来自堆细节。
5. **运动要少。** 5 秒一个动作，比 20 秒十个动作更高级，也更稳定。
6. **文字不进模型。** 任何 logo、标题、标签都在后期合成。
7. **不硬塞马。** 马是原作的锚点，不是所有二创的必需品。

---

## 兼容性

| 场景 | 用法 |
| --- | --- |
| Claude Code / Codex / Cursor | 安装为 Agent Skill，直接点名 `indigo-descent` |
| ChatGPT / Custom GPT | `SKILL.md` 作 Instructions，references 作知识文件 |
| Midjourney | `--sref` + `--sw 150–300` + `--ar 16:9` + `--no photo, 3d, text` |
| Stable Diffusion / ComfyUI | 图生图 + Depth/Lineart + IP-Adapter；按 [图片转译](references/image-transfer.md) 控强度 |
| 即梦 / 可灵 / 通义万相 | 参考图强度 0.45–0.65，风格参考另附静帧 |
| 图生视频 | 5–8 秒、低运动、首帧锁定；按 [运动规则](references/video-motion.md) |

不同模型参数名不同，README 中的数值是**起始建议**，不是硬性参数。

---

## FAQ

**Q：这和直接套 LUT / 滤镜有什么区别？**  
滤镜保留照片的光影与材质，只改颜色；这个 skill 重绘材质、空间和尺度，所以才会“像画”。

**Q：会强制画马吗？**  
不会。马是原作的情感锚点；人像、宠物、产品都不需要马。只有用户明确要“马/下山”时才加。

**Q：人物脸总是崩怎么办？**  
改半身或近景，脸区重绘降到 0.25–0.35，身体与背景分开处理；不要在全景里给脸特写。

**Q：视频总是变形怎么办？**  
缩到 5 秒、运动 1–3/10、只做一个镜头运动；加首帧与尾帧；背景改简单。

**Q：可以商用吗？**  
文本、提示词、流程是 MIT，可自由使用与修改；`assets/` 里的原作静帧、封面、GIF 是 CC BY-NC 4.0，商用需另行授权。生成结果的权利取决于你使用的模型与输入素材。

**Q：和 `ink-wash-journey` 有什么区别？**  
`ink-wash-journey` 是青绿+水墨+田园游历；`indigo-descent` 是靛蓝+朱砂+纸本重彩+巨物微人+电影运动。二者不要混用同一条提示词。

---

## 发布到 GitHub 时

- 仓库名建议：`indigo-descent`
- Description：`A visual skill for restyling any image into the indigo mineral-pigment cinematic world of 《下山》.`
- Topics：`agent-skill` `image-to-image` `image-to-video` `visual-style` `chinese-aesthetic` `mineral-pigment` `prompt-engineering`
- Social preview 用 `assets/cover.jpg`。
- 仓库已控制在 4 MB 以内；不要上传原视频（`1.mp4`–`4.mp4` 共约 350 MB）。
- 如果改过提示词，记得同步 `style.json` 里的默认参数；提示词正文以 `prompts/*.txt` 为准。

---

## 来源与致谢

- 原作：《下山》交互作品，廖慧敏（Hamlin），2025。
- 风格采样：作品中的四段影像 `1.mp4`–`4.mp4`（33.8s / 25.3s / 26.3s / 19.0s，3826×2160）。
- 姐妹篇：《贵州兴义》约 40.4 秒，青绿+水墨+田园游历；本仓库只做对照说明，不包含其素材。
- 本仓库是独立的风格研究，不代表原作方或任何模型厂商。
- 原视频未包含在此仓库；仅保留低分辨率静帧与约 3 秒预览 GIF，用于评论、研究与风格说明。
- 静帧与预览的版权归原作者所有，按 CC BY-NC 4.0 提供；转载或商用请先获得授权。

---

## English

**Indigo Descent** is a portable visual skill distilled from the interactive artwork *Descending the Mountain* (下山). It turns any input image—portrait, pet, product, architecture, landscape, street scene or character—into a cinematic mineral-pigment illustration on warm ivory paper: indigo structure, restrained vermilion and ochre accents, monumental scale, a tiny witness, drifting mist and generous negative space.

It includes a style DNA, an image-transfer workflow (preserve subject, restyle world), image-to-video motion rules, bilingual prompt packs, four worked examples and a quality checklist. It does not train a model or ship weights.

**License:** text and prompts MIT; preview stills, cover and GIF CC BY-NC 4.0. The original artwork and video remain © Liao Huimin (Hamlin). This is an independent style study, not an official release.
