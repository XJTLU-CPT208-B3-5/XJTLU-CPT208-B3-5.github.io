# Campus Navigator Portfolio Website

基于 Jekyll + Agency Theme 的校园导览 App Portfolio 网站。

---

## 网站结构

```
├── _config.yml          # 网站基本配置
├── _data/
│   ├── navigation.yml   # 导航栏设置
│   └── sitetext.yml     # 各页面文字内容
├── _portfolio/          # Portfolio 项目展示（可保留或删除）
├── index.md             # 首页入口
└── assets/               # 图片文件夹
```

---

## 如何修改内容

### 1. 网站基本设置
修改 `_config.yml`：

```yaml
title      : Campus Navigator      # 网站标题
email      : your-email@example.com # 联系邮箱
description: "校园导览App描述"       # 网站描述
author     : CPT208 Team B3-5      # 作者
```

### 2. 导航栏设置
修改 `_data/navigation.yml` 中的 `nav` 列表：

```yaml
en:
  nav:
    - title: "Motivation"    # 显示的文字
      section: motivation    # 对应的页面区块ID
    - title: "Requirements"
      section: requirements
    # ...
```

---

## 5个Portfolio部分内容说明

### Part 1: Motivation & Research
对应 `sitetext.yml` 中的 **services** 区块（section: motivation）

修改 `list` 中的三项：

| 项目 | 说明 |
|------|------|
| **The Why** | 200字陈述：为什么选择Active方向做校园导览 |
| **The Gap** | 4篇学术论文 + 4个商业产品的分析（各列出3个优点和3个不足） |
| **The Stakeholders** | 主要用户和次要用户画像（Personas） |

### Part 2: User Requirements  
对应 `sitetext.yml` 中的 **portfolio** 区块（section: requirements）

目前作为预留区块，建议在 `_portfolio/` 文件夹中添加详细页面，或创建新页面。

可添加内容：
- User Journey Map（用户旅程地图）
- Requirements List（3个"Playful"必要条件）
- Evidence of Life（5张照片/短视频）

### Part 3: Ideation & Alternatives
对应 `sitetext.yml` 中的 **timeline** 区块（section: ideation）

修改 `events` 列表：

| 项目 | 说明 |
|------|------|
| **Crazy Eights** | 8张手绘UI草图照片 |
| **Design Alternatives** | 2-3种设计方案对比说明 |
| **Low-Fi Prototype** | Figma可点击原型链接 |

图片放在 `assets/img/timeline/` 目录

### Part 4: Technical Implementation
对应 `sitetext.yml` 中的 **about** 区块（section: implementation）

修改 `body` 内容，可添加：
- System Architecture（系统架构图）
- High-Fi Prototype（线上演示链接，如 GitHub Pages 或 Vercel）
- Individual Contributions（团队成员分工表格）

### Part 5: Evaluation & Reflection
对应 `sitetext.yml` 中的 **contact** 区块（section: evaluation）

修改标题和描述，可添加：
- Usability Testing（3人测试结果）
- Iterative Refinement（改进前后对比截图）
- Final Reflection（社会/伦理反思 + AI使用说明）

---

## 修改团队成员信息

修改 `_data/sitetext.yml` 中的 `team.people` 列表：

```yaml
team:
  people:
    - name: "成员姓名"
      role: "角色（如：UI设计、代码开发）"
      image: assets/img/team/照片.jpg   # 放入对应图片
      social:
        - url: https://github.com/你的github
          icon: fab fa-github
```

---

## 添加图片

1. 将图片放入对应目录：
   - 团队照片：`assets/img/team/`
   - 时间线图片：`assets/img/timeline/`
   - 客户/评价图片：`assets/img/clients/`

2. 在配置文件中引用路径（不带 `assets/` 前缀）

---

## 本地运行

```bash
# 进入项目目录
cd /path/to/XJTLU-CPT208-B3-5.github.io

# 安装依赖
bundle install

# 运行本地服务器
bundle exec jekyll serve
```

访问 http://localhost:4000

---

## 部署到 GitHub Pages

1. 将代码推送到 GitHub 仓库
2. 进入 Settings → Pages
3. Source 选择 "main branch"
4. 访问 `https://你的用户名.github.io/XJTLU-CPT208-B3-5.github.io/`

---

## 注意事项

- 所有文字内容使用英文（因为主题是英文）
- 修改 `.yml` 文件时注意缩进和格式
- 推送后可能需要等待1-2分钟部署
