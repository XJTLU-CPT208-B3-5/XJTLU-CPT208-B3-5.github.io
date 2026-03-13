# 网站架构调整指南

## 当前文件结构分析

```
XJTLU-CPT208-B3-5.github.io/
├── _config.yml           # 网站基本配置 ✅ 需修改
├── _data/
│   ├── sitetext.yml      # 5个部分的文字内容 ✅ 需填充
│   ├── navigation.yml    # 导航栏配置
│   └── style.yml        # 样式配置
├── _portfolio/           # ⚠️ 建议删除或重构
│   ├── project1.md
│   ├── project2.md
│   └── ... (6个文件)
├── index.md              # 首页入口
├── assets/
│   ├── img/
│   │   ├── timeline/     # 时间线图片 (1.jpg, 2.jpg, 3.jpg, 4.jpg)
│   │   ├── portfolio/    # Portfolio图片 (旧模板)
│   │   ├── team/         # 团队成员照片
│   │   ├── clients/      # 评价/测试图片
│   │   ├── header-bg.jpg # 页头背景
│   │   └── map-image.png # 地图背景
│   └── css/ / js/        # 样式和脚本
└── README.md
```

---

## 推荐架构：单页展示模式

本项目采用 **单页应用 (Single Page)** 架构，所有内容在一个页面展示，通过导航栏跳转。

### 核心文件说明

| 文件 | 作用 | 是否修改 |
|------|------|---------|
| `_config.yml` | 网站标题、描述、作者 | ✅ 需修改 |
| `_data/sitetext.yml` | **所有文字内容** | ✅ 主要修改对象 |
| `_data/navigation.yml` | 导航栏链接 | 视情况修改 |
| `index.md` | 首页入口 | ❌ 无需修改 |
| `_portfolio/` | 旧模板portfolio | ❌ 建议删除 |

---

## 5个部分的内容位置

修改 `sitetext.yml` 中的以下区块：

```
sitetext.yml
├── header           → 首页大标题和副标题
├── services         → Part 1: Motivation & Research (The Why, The Gap, Stakeholders)
├── portfolio        → Part 2: User Requirements  
├── timeline         → Part 3: Ideation & Alternatives (Crazy 8s, Design Alternatives, Low-Fi)
├── about            → Part 4: Technical Implementation
├── clients          → Part 5: Evaluation & Reflection
└── team             → 团队成员信息
```

---

## 架构调整方案

### 方案A：清理旧文件（推荐）

如果 `_portfolio/` 文件夹和 `assets/img/portfolio/` 图片夹不需要，执行：

1. **删除 `_portfolio/` 文件夹**（6个project文件）
2. **删除 `assets/img/portfolio/` 图片夹**（旧模板图片）
3. **保留以下图片目录**：
   - `assets/img/timeline/` - 时间线图片
   - `assets/img/team/` - 团队照片
   - `assets/img/clients/` - 评价图片

清理后的干净结构：

```
├── _config.yml
├── _data/
│   ├── sitetext.yml      ← 所有内容在这里
│   ├── navigation.yml
│   └── style.yml
├── index.md
└── assets/
    └── img/
        ├── timeline/     ← Part 3 图片
        ├── team/         ← 团队照片
        ├── clients/      ← Part 5 图片
        ├── header-bg.jpg
        └── map-image.png
```

### 方案B：重构为多页模式

如果需要更详细的内容展示，可以创建独立页面：

```
_pages/
├── motivation.md    → Part 1 详细页面
├── requirements.md  → Part 2 详细页面
├── ideation.md      → Part 3 详细页面
├── implementation.md → Part 4 详细页面
└── evaluation.md    → Part 5 详细页面
```

然后在 `sitetext.yml` 中将链接指向这些页面。

---

## 如何填充内容

### Part 1: Motivation & Research
在 `sitetext.yml` 的 `services.list` 中修改：

```yaml
services:
  list:
    - title: "The Why"        # 保持不变
      desc: "在这里写200字的陈述..."
    - title: "The Gap"        # 保持不变  
      desc: "在这里写论文和产品分析..."
    - title: "The Stakeholders"  # 保持不变
      desc: "在这里写用户画像..."
```

### Part 2: User Requirements
在 `sitetext.yml` 的 `portfolio` 中修改标题和文字，或创建独立Markdown页面。

### Part 3: Ideation & Alternatives
在 `sitetext.yml` 的 `timeline.events` 中修改事件列表：

```yaml
timeline:
  events:
    - title: "Crazy Eights Sketches"
      year: "Phase 1"
      desc: "描述..."
      image: assets/img/timeline/1.jpg  # 修改图片文件名
```

### Part 4: Technical Implementation
在 `sitetext.yml` 的 `about.body` 中修改描述文字。

### Part 5: Evaluation & Reflection
在 `sitetext.yml` 的 `clients.list` 中修改评价项目。

### Team 成员
在 `sitetext.yml` 的 `team.people` 中修改成员信息。

---

## 图片命名规范

将你的图片放入对应目录，并重命名：

```
assets/img/timeline/
├── 1.jpg        → Crazy Eights Sketches
├── 2.jpg        → Design Alternatives  
├── 3.jpg        → Low-Fi Prototype
└── 4.jpg        → (可选) 其他

assets/img/team/
├── member1.jpg  → 团队成员1照片
├── member2.jpg  → 团队成员2照片
├── member3.jpg  → 团队成员3照片
└── member4.jpg  → 团队成员4照片

assets/img/clients/
├── usability.jpg      → Usability Testing 结果
├── refinement.jpg     → Iterative Refinement
└── reflection.jpg     → Final Reflection
```

---

## 下一步行动

1. **先清理**：删除 `_portfolio/` 和 `assets/img/portfolio/`
2. **再填充**：按 Part 1-5 顺序修改 `sitetext.yml`
3. **加图片**：把对应图片放入 `assets/img/timeline/` 等目录
4. **改团队**：在 `team.people` 中添加成员信息

需要我帮你执行清理或进一步修改吗？
