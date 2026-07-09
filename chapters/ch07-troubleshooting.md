# 第 7 章 GEE 常见问题

## 核心内容

### 7.1 下载影像时超出范围
- 问题：Export.image.toDrive 导出时影像超出范围
- 解决：先 .select(['B4','B3','B2']) 再 .first()，或在 Export 中指定 bands

### 7.2 输入参数无效类型
- 问题：Expected Image, got ImageCollection
- 解决：对 ImageCollection 使用 .mosaic() 或 .median() 聚合为单景影像

### 7.3 影像波段为零
- 问题：筛选时间超出影像实际时间范围
- 解决：检查影像数据集的时间范围（如 MODIS GPP 从 2001 年开始）

### 7.4 导出到 Assets 错误
- 问题：描述名称包含非法字符（斜杠 /）
- 解决：使用字母、数字、连字符和下划线

### 7.5 动画视频导出错误
- 问题：Geometry coordinate projection requires non-zero maxError
- 解决：设置正确的投影参数

### 7.6-7.21 其他常见问题
- 7.6 超出计算内存限制
- 7.7-7.8 影像裁剪相关问题
- 7.9 导出影像为空白
- 7.10-7.12 runTask 相关问题
- 7.13-7.14 图表加载问题
- 7.15-7.16 join 连接问题
- 7.17 reducer 问题
- 7.18 投影错误
- 7.19 影像投影错误
- 7.20 无法解析投影
- 7.21 超出用户内存限制

### 排错原则
1. 仔细阅读错误提示信息
2. 检查数据类型是否匹配（Image vs ImageCollection）
3. 检查时间范围是否在数据集有效范围内
4. 检查导出名称是否合法
5. 查阅 DOS 文档了解函数正确用法