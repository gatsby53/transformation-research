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

---

# sources/

一次情報の参照台帳を保存する。

各企業ごとにフォルダを作成する。

```text
sources/
├── Microsoft/
│   ├── source_index.csv
│   └── reference_docs/
├── Amazon/
│   ├── source_index.csv
│   └── reference_docs/
└── ...
```

## source_index.csv

例：

```csv
company_id,fy,document_type,source_name,url,used_pages,accessed_date,memo
MSFT,1999,Annual Report,Microsoft IR,https://...,34-39,2026-06-29,Financial highlights
MSFT,1999,Market Share,Gartner,https://...,12-13,2026-06-29,Office market share
```

## 原則

* PDF本体は原則保存しない。
* URL、取得日、利用ページを記録する。
* 外部リンク切れリスクが高い資料のみ、例外的にPDFを保存してよい。

## reference_docs/

以下を保存可能。

* Gartner資料
* IDC資料
* 記事PDF
* スクリーンショット
* 消失リスクが高い資料

---

# data/

研究用データを保存する。

## 基本思想

* raw：企業ごとの生データ
* processed：全社横断分析用データ
* features：派生特徴量

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

# data/raw/

各企業の生データ。

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
* 欠損値を許容する。

---

# data/processed/

全企業共通フォーマット。

AI分析、比較分析で利用する。

### financials.csv

1行1企業×1年度。

### segments.csv

1行1企業×1年度×1セグメント。

### markets.csv

1行1企業×1年度×1市場。

### events.csv

1行1企業×イベント。

### features.csv

派生特徴量。

---

# companies/

人間が読むための企業カルテ。

```text
companies/
├── Microsoft.md
├── Amazon.md
└── Nvidia.md
```

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
