# 第 5 章 Python API 安装和语法

## 核心内容

### geemap 安装流程
1. 安装 Miniconda（最小 Python 发行版）
2. 创建独立环境：conda create -n gee python
3. 激活环境：conda activate gee
4. 安装 geemap：conda install -c conda-forge geemap
5. 或使用 Mamba 加速：mamba install -c conda-forge geemap pygis

### Jupyter Notebook 认证
- 导入 ee 和 geemap 包
- geemap.set_proxy(port) 配置代理（如有需要）
- Map = geemap.Map() 创建交互式地图
- 首次运行需在浏览器中完成 Earth Engine 账户认证

### JavaScript vs Python 语法对照
- 代码块：Python 用缩进，JavaScript 用花括号 {}
- 变量：Python 用 var = value，JavaScript 用 var var = value;
- 空值：Python None = JavaScript null/undefined
- 注释：Python # / 多行 #，JavaScript // / /* */
- 列表：Python list = JavaScript array
- 字典：Python dict = JavaScript object
- 逻辑运算符：Python and/or/not = JavaScript &&/||/!
- 类型检查：Python type() = JavaScript typeof
- 条件语句：Python if/elif/else = JavaScript if/else if/else

### Python 核心功能
- 基础概念：ee.Image, ee.FeatureCollection, ee.Geometry 等对象
- 可视化：geemap.Map() 交互式地图
- 数据应用：影像加载、筛选、处理
- 地理数据分析：指数计算、统计分析
- Cartoee 制图：专业地图输出
- 图表制作：Chart 数据可视化
- 常见错误和解决方案：第 5.9 节