# Transformation Research Standard (TRS) v1.0

## 1. Purpose

変身企業の特徴を定量的に分析し、Transformation Theoryを構築する。

---

# 2. Basic Principles

## 2.1 Primary Sources First

優先順位

A：Annual Report / 10-K / 有価証券報告書

B：決算説明資料

C：業界調査会社（IDC、Gartner等）

D：信頼できる二次情報

E：推定

---

## 2.2 Estimation Policy

推定は禁止しない。

ただし以下を必ず保持する。

* Source
* Confidence
* Method

---

## 2.3 Reproducibility

第三者が同じデータを再取得できること。

各データには以下を保持する。

* Source_URL
* Source_Document
* Page

---

# 3. Financial Data

取得対象

* Revenue
* Gross Profit
* Operating Income
* Net Income
* R&D
* CapEx
* Employees

年度（FY）ベースで取得する。

---

# 4. Business Segments

会社の開示セグメントを原則そのまま採用する。

研究用再分類は別列で管理する。

---

# 5. Market Definition

市場は顧客から見て代替可能な製品・サービスで定義する。

市場と会社セグメントは区別する。

---

# 6. Market Share

取得項目

* Market Share (%)
* Market Rank

取得できない年度は空欄を許容する。

---

# 7. Stock Price

基準株価は決算期末終値を採用する。

派生指標

* 1Y Return
* 3Y Return
* 5Y Return
* 10Y Return

---

# 8. Missing Values

欠損値を許容する。

無理な補間は行わない。

---

# 9. Data Philosophy

* Data and hypothesis must be separated.
* Raw data should be preserved.
* AI analysis should be reproducible.
* The ultimate goal is to build Transformation Theory.
