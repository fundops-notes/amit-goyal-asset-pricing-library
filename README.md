# Amit Goyal 文献库

- 建立日期：2026-10-02
- 来源：作者主页 https://sites.google.com/view/agoyal145 （University of Lausanne / Swiss Finance Institute）
- 本仓库：https://github.com/fundops-notes/amit-goyal-asset-pricing-library （公开）
- 全部文件为作者本人公开发布的 PDF 与数据，可自由取用；引用时仍以正式发表版本为准。

## 目录结构

| 文件夹 | 内容 | 篇数 |
| --- | --- | --- |
| 01_宏观择时与股债溢价可预测性 | 股债收益溢价预测、Goyal-Welch 主线 | 5 |
| 02_方法论与统计检验 | 可预测性检验、多重检验、beta vs 特征 | 4 |
| 03_因子异象_动量_流动性 | 动量、流动性、交易成本、空头端 | 9 |
| 04_期权与隐含波动率 | IV 曲面、期权因子结构、事件风险 | 8 |
| 05_信用债与资本成本 | 信用债异象、违约期权定价权益、ML 预测 | 7 |
| 06_资管与私募管理人选择 | 公募/私募管理人选择与 LP 行为 | 5 |
| 07_组合构建与实务 | 均值方差、风险预算、货币对冲、异质风险 | 5 |
| 08_其他 | 亚洲金融危机 | 1 |
| 00_数据集 | Welch-Goyal 预测变量库、个股/因子 beta | 11 |

## 未取到的 5 篇（SSRN 有 Cloudflare 验证，需手动下载）

| 论文 | SSRN 编号 |
| --- | --- |
| Goyal, Nozawa & Qiu (2026), On The Drivers of Corporate Bond Lending | 7392021 |
| Cao, Goyal, Wang, Zhan & Zhang (2024), Opioid Crisis and Firm Downside Tail Risks | 4942686 |
| Bali, Goyal, Mörke & Weigert, In Search of Seasonality in Intraday and Overnight Option Returns | 5386128（已用 CFR 2026-02 版替代） |
| Goyal (2017), No Size Anomalies in U.S. Bank Stock Returns | 2410542 |
| Chordia, Goyal & Tong (2011), Pairwise Correlations | 1785390 |
| Goyal, Welch, Kahl & Torous (2003), A Note on Predicting Returns with Financial Ratios | 486265 |

下载入口格式：https://papers.ssrn.com/sol3/papers.cfm?abstract_id=编号

## 建议阅读顺序

### 第一轮：先建立"什么可信"的判断标准（3 篇，约 2 小时）

1. **Goyal & Welch (2008), A Comprehensive Look at the Empirical Performance of Equity Premium Prediction** — 宏观择时的默认结论是负面的，先看这个再看别的。
2. **Goyal & Jegadeesh (2018), Cross-Sectional and Time-Series Tests of Return Predictability** — 判断别人（和��己）报告的可预测性统计是否可信的尺子。
3. **Chordia, Goyal & Saretto (2020), Anomalies and False Rejections** — 因子回测的多重检验基准。

这三篇读完，后面任何一篇论文里的"我们发现 X 显著"你都会自动打折。

### 第二轮：按自己的业务方向选一条主线

- 做宏观择时/仓位：Goyal-Welch-Ziv (2024) 及其 Internet Appendix → Goyal (2004) 人口结构与资金流 → Goyal & Welch (2003) 股息率
- 做量化选股/因子：Is Momentum an Echo (2015) → Empirical Determinants of Momentum (2025) → Price Impact in Auctions (2026) → Stealthy Shorts (2025)
- 做期权/波动率：Pricing Event Risk (2025) → Goyal & Saretto (2025, IPCA) → Cheap Options Are Expensive (2026) → Joint Factor Model (2025 WP)
- 做信用债/资本成本：Equity Misvaluation and Default Options (2019) → IV Changes and Corporate Bond Returns (2023) → Merton Meets ML (2022 WP)
- 做私募募资/DD：Picking Partners (2026) → Choosing Investment Managers (2024) → Forbearance (2023)
- 做组合搭建：Bad Habits and Good Practices (2015) → Asset Allocation and Bad Habits (2014)

### 第三轮：工具书

- **Goyal (2012), Empirical Cross-Sectional Asset Pricing: A Survey** — 横截面定价领域的地图，碰到不熟的因子先查这里。
- **Chordia, Goyal & Shanken (2017), Betas versus Characteristics** — beta 和特征哪个更基础，是因子构造的关键前置问题。
- **Goyal 的 CV**（00_数据集/Goyal_CV.pdf）— 快速判断某篇论文属于哪条研究线、共著者是谁。

## 数据集说明

| 文件 | 内容 |
| --- | --- |
| WelchGoyal_GW_GWZ_AllInOne_to2025_fullsample.xlsx | 推荐的起步文件，GW(2008) 与 GWZ(2024) 全部预测变量合一，仅全样本版 |
| WelchGoyal_Updated_Data_to2025.xlsx | 2008 论文的更新数据版；2022 年起 lty 取自 FRED，ltr/corpr 取自 Bloomberg 指数 |
| WelchGoyal_2025_Data_to2025_csv.zip / matlab.zip | 同一份数据的面板格式，matlab 版便于直接读入 |
| WelchGoyal_2024_Data_to2021_*.zip | 2022 论文对应数据 |
| WelchGoyal_2008_Original_Data_to2005.zip | 原始版，用于复现 2008 论文的表 |
| 个股beta_Betas.csv (197MB) | IPCA 论文的个股 beta，期权定价与风险中性化用 |
| IPCA_三因子beta_Factors.csv | 三个因子的定义/载荷 |

> 注意：GW/GWZ 数据的预测变量构造有严格的滞后与季调口径，直接拿原始列回测通常会复现不出论文结果。README 里各 zip 内的说明文件务必先读。
