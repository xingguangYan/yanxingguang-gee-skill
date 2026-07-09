# 第 4 章 地球引擎学习和使用教程

## 核心内容

### 单景影像加载
- 使用 ee.Image("DATASET/PATH") 加载
- 设置可视化参数：min, max, bands, palette
- 示例：NASA/NASADEM_HGT/001 DEM 数据

### 影像集合加载与筛选
- 使用 ee.ImageCollection("DATASET") 加载
- filterDate(start, end)：按时间范围筛选
- filter(ee.Filter.lt('property', value))：按属性筛选
- filter(ee.Filter.bounds(geometry))：按空间范围筛选
- CLOUDY_PIXEL_PERCENTAGE：Sentinel-2 云量筛选

### 影像聚合
- collection.median()：中位数聚合
- collection.mosaic()：镶嵌聚合
- collection.mean()/max()/min()：其他聚合方式

### 矢量操作
- 加载矢量：ee.FeatureCollection("DATASET")
- 按属性筛选：filter(ee.Filter.eq('field', 'value'))
- 全球行政区域：FAO/GAUL_SIMPLIFIED_500m/2015/level2
- ui.Map.FeatureViewLayer：快速加载矢量地图

### 底图设置
- Map.setOptions(mapTypeId)：ROADMAP/SATELLITE/HYBRID/TERRAIN
- 自定义样式字典

### 关键函数速查
- ee.Filter.lt(name, value)：小于过滤
- ee.Filter.bounds(geometry)：空间边界过滤
- ee.Filter.date('YYYY-MM-DD')：日期过滤
- Map.addLayer(featureCollection.draw({color, strokeWidth}))：绘制矢量