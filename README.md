# 📡 基于Hadoop、Hive和Spark的电信用户行为分析大数据可视化
## Telecom User Behavior Analysis

> 基于大数据技术栈构建的电信用户上网行为分析系统  
> 覆盖 **数据生成 → 数据采集 → 计算分析 → 可视化展示** 全流程

---

## 📑 目录
- [技术栈](#技术栈)
- [项目结构](#项目结构)
- [可视化分析看板](#可视化分析看板)
- [项目启动指南](#项目启动指南)
- [核心指标说明](#核心指标说明)
- [许可证](#许可证)

---

## 🧰 技术栈
本项目主要使用以下技术组件：
- **数据生成**：Java（Spring Boot）、`data-generator`
- **数据采集**：Apache Flume、DataX
- **数据存储与计算**：Apache Hive（UDF / UDAF）、HDFS
- **数据可视化**：QuickBI / DataV
- **脚本管理**：Shell 脚本

---

## 📁 项目结构

```text
telecom-user-behavior-analysis
├── data-generator      # 数据模拟生成模块（Jar + 配置）
├── scripts             # Flume / Hive / DataX 启动脚本
├── visualization       # 可视化大屏截图及说明
├── hive_udf_custom     # Hive 自定义函数源码及 Jar
├── interceptor         # 数据交换 / 接口脚本
└── README.md           # 项目说明文档
```

---

## 📊 可视化分析看板
本模块展示基于 BI 工具构建的核心分析指标：

### 1️⃣ 仪表盘全景
<img width="2226" height="1104" alt="电信用户行为分析仪表盘全景" src="https://github.com/user-attachments/assets/f8c45a9a-43b7-4227-bf7c-d739d8bad332" />

- 用户地域分布
- 网络制式偏好
- 核心流量指标

### 2️⃣ 网站访问排行榜
<img width="962" height="682" alt="电信用户行为分析_网站访问排行榜" src="https://github.com/user-attachments/assets/c45e6d9c-8ed4-41dd-93b9-a91a28698d98" />

- Top N 高频访问网站
- 搜索类业务（如百度）占主导地位

### 3️⃣ 网络制式统计
<img width="962" height="666" alt="电信用户行为分析_用户访问统计情况分析" src="https://github.com/user-attachments/assets/431116f4-8d19-43d0-afd3-e708a5624e24" />

- 对比 4G / 5G / WIFI
- 流量消耗与访问次数分析

---

## 🚀 项目启动指南

### 1️⃣ 数据生成
```bash
cd data-generator
java -jar behavior-0.0.1-SNAPSHOT.jar
```

### 2️⃣ 数据采集（Flume → HDFS）
```bash
cd scripts
sh log_file_to_hdfs.conf.sh
```

### 3️⃣ 数据计算（Hive ETL）
```bash
hive -f scripts/ads_layer.sql
```

### 4️⃣ 数据导出（DataX → MySQL）
```bash
python datax.py scripts/ads_user_city.json
python datax.py scripts/ads_visit_type.json
```

---

## 📈 核心指标说明
| 指标名称 | 描述 | 业务价值 |
|--------|------|---------|
| 🔥 热门网站 TopN | 访问次数最多的网站域名 | 精准广告推荐 |
| 📶 网络制式分布 | 4G / 5G / WIFI 流量占比 | 网络资源优化 |
| 🗺️ 地域流量分布 | 各省市流量热力图 | 基站扩容规划 |

---

## 📄 许可证
Apache License 2.0
