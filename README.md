# A-Share MCP Financial Data Analysis Tool

一个基于Baostock的A股金融数据分析工具，集成了数据获取、新闻爬取和AI分析功能。

## 功能特性

### 📈 股票数据
- K线数据获取（日线、周线、月线）
- 股票基本信息查询
- 分红派息数据
- 复权因子数据

### 💰 财务数据
- 盈利能力分析
- 运营能力分析
- 成长能力分析
- 资产负债表数据
- 现金流量数据
- 杜邦分析数据

### 📊 市场数据
- 沪深300成分股
- 中证500成分股
- 深证50成分股
- 行业分类数据
- 交易日历

### 🌍 宏观经济数据
- 存款/贷款利率
- 存款准备金率
- 货币供应量（M0、M1、M2）

### 🔍 智能新闻分析
- 网络新闻爬取
- AI风险评估（1-5级）
- AI情感分析（1-5级）

## 安装依赖

```bash
pip install -r requirements.txt
```

## 快速开始

```python
from src.baostock_data_source import BaostockDataSource

# 初始化数据源
data_source = BaostockDataSource()

# 获取股票K线数据
k_data = data_source.get_historical_k_data(
    code="sh.600000",
    start_date="2023-01-01",
    end_date="2023-12-31"
)

# 爬取和分析新闻
news_result = data_source.crawl_news("平安银行", top_k=5)
print(news_result)
```

## 测试

运行完整功能测试：

```bash
python test_baostock.py
```

## 项目结构

a-share-mcp-is-just-i-need/ ├── src/ │ ├── init.py │ ├── data_source_interface.py # 数据源接口定义 │ ├── baostock_data_source.py # Baostock实现 │ └── utils.py # 工具函数 ├── test_baostock.py # 功能测试 ├── requirements.txt # 依赖列表 └── README.md # 项目说明


## 技术栈

- **数据源**: Baostock API
- **网页爬取**: requests + BeautifulSoup
- **AI模型**: Transformers + LoRA微调
- **数据处理**: pandas
- **日志**: Python logging

## 注意事项

1. 需要稳定的网络连接访问Baostock API
2. AI模型文件较大，需要足够的存储空间
3. 建议使用GPU加速AI分析功能

## License

MIT License