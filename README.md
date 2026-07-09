# 🌍 生态地理遥感云计算 GEE Skill

> Google Earth Engine 遥感云计算技术手册 — 从入门到实战的全栈指南

![GEE](https://img.shields.io/badge/GEE-JavaScript%20%2B%20Python-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Status](https://img.shields.io/badge/status-active-success)

---

## 📖 关于本书

本 Skill 基于闫星光、马天跃、李晶、杨荻编著的《生态地理遥感云计算》（北京航空航天大学出版社，2025年），将全书 8 章、504 千字的技术内容提炼为结构化的 Agent 可执行技能。

## 🎯 适用场景

- ✅ 使用 GEE JavaScript API 进行遥感影像处理和分析
- ✅ 使用 Python (geemap/earthengine-api) 进行批量数据处理
- ✅ 计算 NDVI、NDBI、NBR 等光谱指数
- ✅ 加载和处理 Landsat、MODIS、Sentinel 等卫星数据
- ✅ 影像去云、投影变换、掩膜、镶嵌、裁剪
- ✅ 土地覆盖分类、植被监测、水资源分析
- ✅ 构建 GEE Web UI 和交互式应用
- ✅ 排查和解决 GEE 常见错误

## 📚 章节索引

| 章节 | 内容 | 文件大小 |
|------|------|----------|
| [第 1 章](chapters/ch01-cloud-platforms.md) | 云平台概述 | GEE、PIE-Engine、Planetary Computer 等平台对比 |
| [第 2 章](chapters/ch02-gee-platform.md) | GEE 平台基本简介 | 平台工具、配额管理、账号申请 |
| [第 3 章](chapters/ch03-js-syntax.md) | GEE 基础语法和概念 | ee.Image、ee.FeatureCollection、几何对象等核心模型 |
| [第 4 章](chapters/ch04-tutorials.md) | 地球引擎学习和使用教程 | 影像加载、筛选、聚合、可视化全流程 |
| [第 5 章](chapters/ch05-python-api.md) | Python API 安装和语法 | geemap 安装、JS/Python 语法对照 |
| [第 6 章](chapters/ch06-ui-app.md) | GEE UI 和 APP | 面板、布局、部件、交互开发 |
| [第 7 章](chapters/ch07-troubleshooting.md) | GEE 常见问题 | 21 类常见错误及解决方案 |
| [第 8 章](chapters/ch08-datasets.md) | GEE 云平台数据集 | Landsat/MODIS/Sentinel 等数据集速查 |

## 🧰 核心资源

| 文件 | 说明 |
|------|------|
| [SKILL.md](SKILL.md) | 主 Skill 文件，包含核心框架和主题索引 |
| [glossary.md](glossary.md) | 术语表（GEE/geemap/earthengine-api 等核心术语） |
| [patterns.md](patterns.md) | 技术模式（影像加载/筛选/聚合/可视化/导出等常用模式） |
| [cheatsheet.md](cheatsheet.md) | JavaScript/Python API 速查表 |

## 🔑 核心框架

### GEE 双 API 体系
- **JavaScript API**：Code Editor 在线开发，适合交互式地图可视化、快速原型
- **Python API (earthengine-api + geemap)**：适合批量处理、自动化脚本、与本地数据集成
- 两者语义高度对应，掌握一种后可快速迁移至另一种

### 遥感云计算工作流
`
数据加载 → 预处理（去云/投影/筛选/掩膜） → 分析（指数/波段/reducer/时序）
→ 可视化（Map/Chart/颜色映射） → 导出（Drive/Assets）
`

### 懒加载计算模型
GEE 使用惰性计算，只在渲染地图时加载当前视口范围内的数据，避免不必要的全局计算。

## 📊 主要卫星数据集

| 卫星系列 | 分辨率 | 时间跨度 | GEE 数据集路径 |
|---------|--------|---------|----------------|
| Landsat 5/7/8/9 | 30m | 1984-至今 | LANDSAT/LT05/C01/T1, LANDSAT/LC08/C01/T1 |
| MODIS | 250m-1km | 2000-至今 | MODIS/006/MOD09GA, MODIS/006/MCD12Q1 |
| Sentinel-1 | 5-400m | 2014-至今 | COPERNICUS/S1_GRD |
| Sentinel-2 | 10-60m | 2015-至今 | COPERNICUS/S2_SR, COPERNICUS/S2_SR_HARMONIZED |

## 🚀 快速开始

### JavaScript (Code Editor)
`javascript
// 加载 Landsat 8 影像
var image = ee.Image('LANDSAT/LC08/C01/T1_TOA/LC08_123456_20200101');

// 真彩色可视化
var visParams = {bands: ['B4', 'B3', 'B2'], min: 0, max: 0.3};
Map.addLayer(image, visParams, 'Landsat True Color');

// 计算 NDVI
var ndvi = image.normalizedDifference(['B5', 'B4']).rename('NDVI');
Map.addLayer(ndvi, {min: 0, max: 1, palette: ['red', 'yellow', 'green']}, 'NDVI');
`

### Python (geemap)
`python
import ee
import geemap

# 初始化
Map = geemap.Map()

# 加载影像并显示
l8 = ee.Image('LANDSAT/LC08/C01/T1_TOA').select(['B4', 'B3', 'B2'])
Map.add_layer(l8, {'bands': ['B4', 'B3', 'B2'], 'min': 0, 'max': 0.3}, 'Landsat 8')
Map
`

## 📦 安装 geemap

`ash
conda create -n gee python
conda activate gee
conda install -c conda-forge geemap
`

## 📖 推荐阅读顺序

1. **初学者**：第 1 章 → 第 2 章 → 第 3 章 → 第 4 章（基础教程）
2. **进阶用户**：第 4 章（中级/高级教程）→ 第 5 章（Python API）
3. **应用开发**：第 6 章（UI/App 开发）
4. **问题排查**：第 7 章（常见问题速查）
5. **数据查阅**：第 8 章（数据集速查表）

## ⚠️ 注意事项

- 本书内容基于 GEE 2025 年前的 API 版本，部分 API 可能有更新
- 导出影像前需确保筛选时间在数据集有效范围内
- 使用 Export 时，ImageCollection 需先聚合为单景影像
- 导出名称不能包含斜杠 / 等特殊字符

## 📄 版权说明

本书版权归北京航空航天大学出版社所有。本 Skill 仅为技术内容的结构化提取和学习用途，不包含原书全文内容。

## 🔗 相关链接

- [Google Earth Engine Code Editor](https://code.earthengine.google.com/)
- [GEE Documentation](https://developers.google.com/earth-engine)
- [geemap 文档](https://geemap.org/)
- [PIE-Engine](https://engine.piesat.cn/engineStudio)
- [Planetary Computer](https://planetarycomputer.microsoft.com/)

---

Made with ❤️ by 闫星光