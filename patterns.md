# 技术模式与技法

## 影像加载模式
- 单景影像：ee.Image("DATASET/PATH")
- 影像集合：ee.ImageCollection("DATASET").filterDate(start, end)
- 矢量数据：ee.FeatureCollection("DATASET")

## 影像筛选模式
- 时间筛选：.filterDate('YYYY-MM-DD', 'YYYY-MM-DD')
- 空间筛选：.filter(ee.Filter.bounds(geometry))
- 云量筛选：.filter(ee.Filter.lt('CLOUDY_PIXEL_PERCENTAGE', 30))
- 属性筛选：.filter(ee.Filter.eq('field', 'value'))

## 影像聚合模式
- 中位数：collection.median()
- 镶嵌：collection.mosaic()
- 均值：collection.mean()

## 可视化模式
- 基础参数：{bands: ['B4','B3','B2'], min: 0, max: 3000}
- 调色板：{bands: ['dem'], min: -3, max: 18, palette: ['000000', ...]}
- 随机颜色：{color: featureCollection.randomVisualizer}

## 导出模式
- 先聚合为单景再用 Export.image.toDrive
- 描述名称不含斜杠等特殊字符
- 确保筛选时间在数据集有效范围内

## 投影处理
- 导出时指定正确的 crs 参数
- 使用 .select() 指定波段后再导出