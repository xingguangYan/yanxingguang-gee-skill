# GEE 速查表

## JavaScript API 速查

### 加载数据
- 单景影像：ee.Image(DATASET/PATH)
- 影像集合：ee.ImageCollection(DATASET)
- 矢量集合：ee.FeatureCollection(DATASET)
- 点几何：ee.Geometry.Point([lon, lat])
- 面几何：ee.Geometry.Polygon([[coords]])

### 筛选操作
- 时间范围：filterDate(start, end)
- 空间范围：filter(ee.Filter.bounds(geometry))
- 属性等于：filter(ee.Filter.eq(field, value))
- 属性小于：filter(ee.Filter.lt(field, value))
- 日历范围：filter(ee.Filter.calendarRange(year, year, year))
- 云量筛选：filter(ee.Filter.lt(CLOUDY_PIXEL_PERCENTAGE, 20))

### 聚合操作
- 中位数：collection.median()
- 镶嵌：collection.mosaic()
- 均值：collection.mean()
- 最大值：collection.max()
- 最小值：collection.min()

### 可视化参数
- bands：波段列表如 B4 B3 B2
- min：最小值
- max：最大值
- palette：调色板颜色数组

### 导出操作
- 导出到 Drive：Export.image.toDrive({image, description, region, scale})
- 导出到 Assets：Export.image.toAsset({image, assetId, description})

## Python API (geemap) 速查

### 初始化
- import ee
- import geemap
- Map = geemap.Map()

### 安装
- conda create -n gee python
- conda activate gee
- conda install -c conda-forge geemap