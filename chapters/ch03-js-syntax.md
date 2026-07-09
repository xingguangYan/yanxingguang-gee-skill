# 第 3 章 GEE 基础语法和概念

## 核心内容

### JavaScript 编译界面
- Code Editor 在线 IDE，支持实时代码执行和地图可视化
- 代码链接分享：URL 中含 hideCode=true 可隐藏代码仅展示结果
- 左侧代码面板 + 右侧地图面板 + Console 输出

### JavaScript 数据类型
- 字符串 String 类型，支持拼接和格式化
- 数字 Number 类型，整数和浮点数
- 列表 ee.List，有序集合，支持索引访问
- 字典 ee.Dictionary，键值对映射
- 数组 ee.Array，多维数值数组

### 矢量数据模型
- ee.Geometry：点、线、面、多边形等几何对象
  - ee.Geometry.Point([lon, lat])
  - ee.Geometry.Polygon([[coords]])
- ee.Feature：带属性的几何要素
  - ee.Feature(geometry, properties)
- ee.FeatureCollection：要素集合
  - 支持 aggregate_max/min/mean 等聚合操作
  - 支持 filter、merge、draw 等操作
  - randomPoints(geometry, count, seed) 生成随机采样点

### 影像数据模型
- ee.Image：单景影像，由多个波段组成
  - ee.Image("DATASET/PATH") 加载数据集
  - ee.Image.constant(value) 创建常量影像
  - ee.Image.cat([img1, img2]) 合并多波段
  - addBands() 添加新波段
  - select(['old'], ['new']) 重命名波段
- ee.ImageCollection：影像集合
  - dataset.select('bandName') 选择波段
  - 可视化参数：bands, min, max, palette
- Map 控制：
  - Map.setCenter(lon, lat, zoom) 设置中心点和缩放
  - Map.addLayer(object, visParams, name) 添加图层
  - Map.setOptions(mapTypeId) 切换底图类型

### 核心对象关系
- Geometry 到 Feature 到 FeatureCollection 是矢量数据链
- Image 到 ImageCollection 是影像数据链
- Map.addLayer() 负责可视化渲染