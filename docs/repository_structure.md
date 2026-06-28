# Repository Structure

## Purpose

本リポジトリは、変身企業（Transformation Company）の定量研究を行うための研究基盤である。

目的は以下。

* 企業の時系列データを蓄積する
* 第一成功、第一変身、第二変身を定量的に分析する
* 100社規模の比較研究を行う
* 変身企業理論（Transformation Theory）を構築する

---

# Repository Structure

```text
transformation-research/
│
├── README.md
│
├── docs/
├── sources/
├── data/
├── companies/
├── prompts/
├── scripts/
├── outputs/
└── journal/
```

---

# docs/

研究ルールおよび設計思想を保存する。

```text
docs/
├── TRS_v1.0.md
├── repository_structure.md
├── data_dictionary.md
└── roadmap.md
```

## 内容

### TRS_v1.0.md

Transformation Research Standard。

データ取得ルール、定義、分析方針を記載する。

---

### repository_structure.md

本ドキュメント。

---

### data_dictionary.md

データ項目の定義。

例：

* revenue
* operating_income
* market_share

など。

---

### roadmap.md

研究の進行計画。

---

# sources/

一次情報を保存する。

各企業ごとにフォルダを作成する。

```text
sources/
├── Microsoft/
├── Amazon/
├── Nvidia/
└── …
```

## 保存対象

* Annual Report
* 10-K
* 有価証券報告書
* 決算説明資料
* Gartner資料
* IDC資料
* Synergy Research資料
* URLメモ
* PDF

### 目的

第三者が同じデータを再取得できる状態を維持すること。

---

# data/

研究用データを保存する。

## 基本思想

### raw

企業ごとの生データ。

### processed

全社横断分析用データ。

### features

派生特徴量。

---

```text
data/
├── raw/
│   ├── Microsoft/
│   ├── Amazon/
│   └── Nvidia/
│
├── processed/
│   ├── company_master.csv
│   ├── financials.csv
│   ├── segments.csv
│   ├── markets.csv
│   ├── events.csv
│   └── features.csv
│
└── features/
```

---

## raw/

各企業の生データを保存する。

例：

```text
data/raw/Microsoft/
├── financials.csv
├── segments.csv
├── markets.csv
├── events.csv
└── notes.md
```

### 方針

* 一次情報に近い形で保存する。
* 推定値を混ぜない。
* 欠損を許容する。

---

## processed/

全企業共通フォーマット。

AI分析、比較分析で利用する。

### financials.csv

1行1企業×1年度。

```text
company_id
fy
revenue
gross_profit
operating_income
net_income
employees
r_and_d
capex
```

---

### segments.csv

1行1企業×1年度×1セグメント。

```text
company_id
fy
segment
segment_revenue
segment_ratio
```

---

### markets.csv

1行1企業×1年度×1市場。

```text
company_id
fy
market
market_share
market_rank
```

---

### events.csv

```text
company_id
event_date
event_type
description
```

---

### features.csv

派生特徴量。

```text
company_id
fy
largest_segment_ratio
second_pillar_ratio
operating_margin
transformation_stage
```

---

# companies/

人間が読むための企業カルテ。

```text
companies/
├── Microsoft.md
├── Amazon.md
└── Nvidia.md
```

## 内容

* 企業概要
* 年表
* 第一成功
* 第一変身
* 第二変身
* 仮説
* 未解決論点

---

# prompts/

AIへ渡す固定プロンプト。

```text
prompts/
├── compare_companies.md
├── analyze_transformation.md
└── generate_company_report.md
```

---

# scripts/

Pythonスクリプト。

```text
scripts/
├── build_timeline.py
├── calc_features.py
├── export_compare.py
└── merge_processed.py
```

---

# outputs/

分析結果。

```text
outputs/
├── charts/
├── company_compare/
└── reports/
```

---

# journal/

研究日誌。

```text
journal/
└── research_log.md
```

## 記録内容

* 仮説
* 気付き
* 修正理由
* 今後の課題

---

# Data Flow

```text
sources
↓
data/raw
↓
data/processed
↓
features
↓
outputs
↓
theory update
```

---

# Design Philosophy

1. 一次情報を重視する。
2. 推定値は明示する。
3. データと推論を分離する。
4. AIによる自然言語分析を前提とする。
5. 再現可能な研究基盤を構築する。
6. 最終目的は変身企業理論の構築である。
