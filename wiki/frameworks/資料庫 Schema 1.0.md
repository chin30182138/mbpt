---
type: framework
created: 2026-06-12
updated: 2026-06-12
status: active
tags:
  - mbpt
  - schema
  - database
  - v36
sources:
  - "G:/我的雲端硬碟/HJC6.6最新/Data/hjc.db"
  - "[[MBPT V36 升級總覽]]"
  - "[[旺衰計分規格]]"
  - "[[AI 分析流程規格]]"
---

# 資料庫 Schema 1.0

## 目標

`Schema 1.0` 的目標，是把舊 `Case + Tag + Note` 的平面結構，升級成能支援排盤、計分、人格映射、AI 報告與人工覆核的資料模型。

## 舊系統主要問題

舊 `HJC` 結構的優點是簡單，但不足之處是：

- 卦象中間狀態沒有入庫
- 規則命中沒有獨立表
- 人格候選沒有表
- AI 輸出沒有版本欄位
- 長文字過多，結構化欄位不足

## 新核心實體

### 1. Case

案例主檔，保存：

- 個案標題
- 問題類型
- 個案對象
- 建立時間
- 來源系統
- 原始描述

### 2. Chart

保存排盤結果：

- 年月日時干支
- 六爻線值
- 本卦 / 變卦
- 世應位置
- 起卦方式

### 3. YaoState

逐爻保存：

- 爻位
- 六親
- 六獸
- 地支
- 動靜
- 旬空
- 化進 / 化退
- 伏神資訊

### 4. StrengthScore

保存旺衰計分：

- score target
- 各項分數
- 最終分數
- 理由列表
- scoring version

### 5. Type72Profile

七十二型主檔：

- 型號代碼
- 六獸
- 地支
- 型名
- 核心動機
- 焦慮核心
- 防衛模式
- 關係風格

### 6. Type72Candidate

保存某次案例分析產生的人格候選：

- case id
- analysis run id
- type code
- rank
- confidence score
- evidence summary

### 7. Evidence

保存推理證據：

- evidence type
- source location
- structured value
- explanation
- weight

### 8. AnalysisRun

保存一次完整分析：

- case id
- rule engine version
- prompt version
- analysis mode
- run status
- created time

### 9. AIReport

保存報告輸出：

- analysis run id
- report type
- report content
- model name
- prompt version
- edited by human

### 10. ReviewResult

保存人工覆核：

- accepted
- revised conclusion
- reviewer
- review note
- review time
