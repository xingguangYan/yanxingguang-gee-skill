---
name: yanxingguang-gee
description: Google Earth Engine (GEE) 遥感云计算技术手册。基于闫星光《生态地理遥感云计算》一书，涵盖 GEE JavaScript/Python API、影像处理、指数反演、时空分析、UI/App 开发和云平台数据集。Use when the user needs to process remote sensing data with GEE, calculate spectral indices, perform land cover classification, work with Landsat/MODIS/Sentinel data, debug GEE errors, or build GEE web applications.
---

# 生态地理遥感云计算 GEE Skill

原书：《生态地理遥感云计算》，闫星光、马天跃、李晶、杨荻 编著，北京航空航天大学出版社，2025
核心框架：Google Earth Engine 遥感云计算平台的全栈技术体系

## 核心框架

### GEE 双 API 体系
- JavaScript API：Code Editor 在线开发，适合交互式地图可视化、快速原型
- Python API (earthengine-api)：适合批量处理、自动化脚本、与本地数据集成
- 两者语义高度对应，掌握一种后可快速迁移至另一种

### 遥感云计算工作流
1. 数据加载：从 Earth Engine 数据集目录加载影像/矢量
2. 预处理：去云、投影变换、筛选、掩膜
3. 分析：指数计算、波段运算、reducer 统计、时序分析
4. 可视化：Map/Chart 渲染、颜色映射、图层叠加
5. 导出：下载到本地或 Google Drive

### 懒加载计算模型
GEE 使用惰性计算，只在渲染地图时加载当前视口范围内的数据，减少运算量。理解这一点可以避免不必要的全局计算。

## 章节索引

| 章 | 标题 | 文件 |
|----|------|------|
| 1 | 云平台概述 | ch01 |
| 2 | GEE 平台基本简介 | ch02 |
| 3 | GEE 基础语法和概念 | ch03 |
| 4 | 地球引擎学习和使用教程 | ch04 |
| 5 | Python API 安装和语法 | ch05 |
| 6 | GEE UI 和 APP | ch06 |
| 7 | GEE 常见问题 | ch07 |
| 8 | GEE 云平台数据集 | ch08 |

## 主题索引

- 指数计算 (NDVI/NDBI/NBR) → ch04, ch05
- 影像去云 (Cloud Masking) → ch04, ch07
- Landsat/MODIS/Sentinel 数据加载 → ch08
- 矢量和影像互转 → ch04
- Reducer 统计 (mean/median/max/min) → ch04
- Join 连接操作 → ch04
- 线性回归与相关性分析 → ch04
- 投影与重投影 (EPSG) → ch04, ch07
- GEE 配额与计算资源管理 → ch02, ch07
- Chart 图表制作 → ch05
- Cartoee 制图 → ch05
- GEE App 部署 → ch06
- Python earthengine-api 安装配置 → ch05
- 常见错误排查 → ch07

## Reload
- 重启会话即可

## Share this skill
  gh skill publish /yanxingguang-gee