# 第 6 章 GEE UI 和 APP

## 核心内容

### GEE 内置 APP 案例
- Ocean Timeseries Investigator：MODIS 海洋温度时序监测
- Linked Maps：分屏联动地图（真彩色/假彩色/水域/植被四屏对比）
- Split Panel：滑动地图（不同时期影像对比）
- Mosaic Editor：区域单景影像合成（中位数聚合）
- Global Population Explorer：全球人口分布统计
- Global Forest Change Explorer：全球森林变化探索

### UI 开发四要素
1. **面板 (Panel)**：ui.Panel 是上层 UI 容器，控制小部件排列
2. **根 (Root)**：ui.root 固定面板，容纳所有 UI 内容
3. **布局 (Layout)**：ui.Panel.Layout
   - 流动布局：horizontal / vertical
   - 绝对布局：top-left, top-center, top-right, middle-left, middle-right, bottom-left, bottom-center, bottom-right
4. **部件 (Widget)**：Button, Chart, Checkbox, Label, Listbox, Panel, Slider, Table, Textarea, TextField, Toggle

### 关键函数
- ui.Button(label, onClick)：创建按钮
- ui.Chart(dataTable, chartType)：创建图表
- ui.Map.FeatureViewLayer(assetId)：快速加载矢量
- Map.addLayer()：添加图层到地图
- ui.root.clear()：清空根面板

### APP 开发案例
- 交互式地图开发
- 多图层叠加控制
- 图表与地图联动
- 其他优秀 APP 案例参考