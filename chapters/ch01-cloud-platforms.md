# 第 1 章 云平台概述

## 核心内容

### 遥感云平台格局
- **GEE (Google Earth Engine)**：行业标杆，70+ PB 数据，数百万用户，JavaScript + Python 双 API
- **Planetary Computer (微软)**：Python/R API，Azure 计算环境，高分辨率独家数据集
- **CODE-DE (德国)**：哥白尼卫星数据，EO-Browser/EO-Finder/Jupyter Notebook 三件套
- **MAAP (NASA+ESA)**：聚焦森林碳动态，BIOMASS/GEDI/NISAR 任务数据
- **PIE-Engine (航天宏图)**：国内最成熟遥感云平台，JS+Python 双 API，184 个数据集
- **AI Earth (阿里云)**：面向地球科学的云平台

### GEE 核心架构
- 基于 Google Borg 集群管理系统、分布式数据库、Google 文件系统
- FlumeJava 框架支持并行管道执行
- 懒加载计算模型：只加载当前视口范围数据

### 关键对比
| 平台 | API | 数据量 | 特色 |
|------|-----|--------|------|
| GEE | JS + Python | 70+ PB | 生态最成熟 |
| PIE-Engine | JS + Python | 6.33 PB | 国内首选 |
| Planetary Computer | Python + R | PB 级 | 高分辨率独家数据 |