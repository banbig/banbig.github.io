# 博客网站个性化任务清单

本文档记录了将 AstroWind 模板简化并替换为个人内容的详细任务清单，同时保持项目框架结构和多语言支持。

## 🎯 总体目标
- 简化网站内容，保留核心博客功能
- 替换所有示例内容为个人内容
- 保持多语言支持框架
- 维护项目整体架构不变

---

## 📋 任务清单

### 阶段 1: 基础配置更新

#### 1.1 站点基本信息配置
- [ ] **文件**: `src/config.yaml`
  - [ ] 修改站点名称 (name: AstroWind → 你的站点名称)
  - [ ] 更新站点 URL (site: 'https://astrowind.vercel.app' → 你的域名)
  - [ ] 替换 SEO 描述文字
  - [ ] 更新 Open Graph 图片路径
  - [ ] 修改 Twitter 社交账号信息
  - [ ] 删除 Google Site Verification ID (设为 null)

#### 1.2 导航菜单简化
- [ ] **文件**: `src/navigation.ts`
  - [ ] 简化 headerData.links，保留核心页面:
    - [ ] 首页 (Home)
    - [ ] 关于 (About)
    - [ ] 博客 (Blog)
    - [ ] 联系 (Contact)
  - [ ] 删除 "Homes" 和复杂的 "Pages" 下拉菜单
  - [ ] 更新 footerData，简化链接结构
  - [ ] 修改 footer 版权信息和社交链接
  - [ ] 更新 GitHub 链接为你的仓库

#### 1.3 项目信息更新
- [ ] **文件**: `package.json`
  - [ ] 修改项目名称 (name)
  - [ ] 更新项目描述 (description)

### 阶段 2: 页面内容替换

#### 2.1 首页个性化
- [ ] **文件**: `src/pages/index.astro`
  - [ ] 修改页面 metadata title
  - [ ] 更新 Hero 组件内容:
    - [ ] 替换主标题文字
    - [ ] 修改副标题描述
    - [ ] 更新行动按钮文字和链接
    - [ ] 替换 Hero 图片
  - [ ] 简化或删除不需要的 Widget 组件:
    - [ ] Features、Features2 (功能展示)
    - [ ] Steps (步骤说明)
    - [ ] Stats (统计数据)
    - [ ] 保留 BlogLatestPosts (最新博文)
    - [ ] 保留 CallToAction (行动召唤)

#### 2.2 关于页面
- [ ] **文件**: `src/pages/about.astro`
  - [ ] 替换页面标题和描述
  - [ ] 更新个人/公司介绍内容
  - [ ] 替换相关图片

#### 2.3 联系页面
- [ ] **文件**: `src/pages/contact.astro`
  - [ ] 更新联系信息
  - [ ] 修改联系表单配置（如果需要）
  - [ ] 替换地址、电话等信息

#### 2.4 删除不需要的页面
- [ ] 删除 `src/pages/pricing.astro`
- [ ] 删除 `src/pages/services.astro`
- [ ] 删除 `src/pages/homes/` 目录及其所有文件
- [ ] 删除 `src/pages/landing/` 目录及其所有文件

### 阶段 3: 博客内容清理

#### 3.1 清理示例博文
- [ ] **目录**: `src/data/post/`
  - [ ] 删除 `astrowind-template-in-depth.mdx`
  - [ ] 删除 `get-started-website-with-astro-tailwind-css.md`
  - [ ] 删除 `how-to-customize-astrowind-to-your-brand.md`
  - [ ] 删除 `landing.md`
  - [ ] 保留 `markdown-elements-demo-post.mdx` 作为格式参考（可选）
  - [ ] 删除 `useful-resources-to-create-websites.md`

#### 3.2 创建初始博文
- [ ] 创建第一篇博文: `welcome.md`
  - [ ] 包含正确的 frontmatter 格式
  - [ ] 设置合适的 category 和 tags
  - [ ] 添加发布日期
- [ ] 创建第二篇博文作为示例（可选）

### 阶段 4: 品牌元素更新

#### 4.1 图片资源
- [ ] **目录**: `src/assets/images/`
  - [ ] 替换 `hero-image.png` 为你的图片
  - [ ] 替换 `default.png` (OpenGraph 默认图片)
  - [ ] 添加个人头像或 Logo

#### 4.2 样式微调（可选）
- [ ] **文件**: `src/components/CustomStyles.astro`
  - [ ] 根据需要调整主题色彩
  - [ ] 自定义字体或其他样式

### 阶段 5: 最终检查

#### 5.1 多语言支持确认
- [ ] 确认 `src/config.yaml` 中 i18n 配置完整
- [ ] 验证 `language: en` 和 `textDirection: ltr` 设置正确

#### 5.2 功能测试
- [ ] 运行 `npm run dev` 测试开发环境
- [ ] 检查博客列表页面正常工作
- [ ] 测试文章页面显示正确
- [ ] 验证导航菜单链接正常
- [ ] 检查响应式设计在移动端正常

#### 5.3 代码质量检查
- [ ] 运行 `npm run check` 确保代码质量
- [ ] 修复任何 ESLint 或 Prettier 警告
- [ ] 运行 `npm run build` 确保构建成功

---

## 📝 注意事项

### 保持不变的重要部分
- ✅ **项目架构**: 不要修改 `src/components/` 组件结构
- ✅ **博客系统**: 保持 `src/content/config.ts` 配置不变
- ✅ **路由系统**: 保持 `src/pages/[...blog]/` 动态路由
- ✅ **工具函数**: 保持 `src/utils/` 下的工具函数
- ✅ **多语言框架**: 保持 i18n 基础设施完整

### 文件修改原则
1. **优先编辑**: 尽量编辑现有文件而不是创建新文件
2. **保持格式**: 维持原有的代码格式和结构
3. **渐进替换**: 逐步替换内容，测试每个变更
4. **备份重要**: 在大改动前建议创建 Git 分支

---

## 🚀 完成后的效果

完成所有任务后，你将拥有：
- 一个干净、个性化的博客网站
- 保留了 AstroWind 的优秀架构和性能
- 支持多语言扩展的基础设施
- 完整的博客功能（文章、分类、标签）
- 现代化的 SEO 和性能优化

---

**最后更新**: 2025-08-13
**项目状态**: 🔄 进行中