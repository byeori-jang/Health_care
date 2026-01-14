# 🍺🚬 Smoking & Drinking Health Indicator Analysis (개인 분석)

본 프로젝트는 대규모 건강검진 데이터를 활용하여  
**음주(DRK_YN) 및 흡연(SMK_stat_type_cd)**과  
가장 밀접한 관련을 가지는 **건강 지표를 데이터 기반으로 도출**하는 것을 목표로 한 개인 분석 프로젝트입니다.

특정 지표를 사전에 가정하지 않고,  
**상관관계 분석을 통해 실제로 음주·흡연과 연관성이 큰 지표를 선별**하였습니다.

분석 전 과정은 `smoking_drinking_analysis.ipynb` 노트북에 정리되어 있습니다.

---

## 🔍 분석 목적
- 음주 및 흡연과 **가장 관련이 깊은 건강 지표 도출**
- 단일 지표가 아닌 **생활습관이 인체에 미치는 영향 범위 분석**
- 이후 심화 분석 또는 모델링을 위한 **핵심 변수 선별 근거 확보**

---

## 📂 파일 구성

| 파일명 | 설명 |
|---|---|
| `smoking_driking_dataset.csv` | 건강검진 원본 데이터 |
| `smoking_drinking_analysis.ipynb` | EDA 및 상관관계 분석 노트북 |
| `README.md` | 프로젝트 설명 문서 |

---

## 📊 데이터 개요

- **Dataset**: Health Checkup Dataset
- **표본 수**: 991,346명
- **결측치**: 없음
- **변수 구성**
  - 행동 변수: 음주, 흡연
  - 임상/건강 지표: 간 기능, 혈액, 대사, 혈압 등

---

## 🎯 주요 분석 변수

### 🔹 행동 변수
- `DRK_YN`
  - 0: 비음주
  - 1: 음주
- `SMK_stat_type_cd`
  - 1: 비흡연
  - 2: 과거흡연
  - 3: 현재흡연

### 🔹 건강 지표
- 간 기능: `gamma_GTP`, `SGOT_AST`, `SGOT_ALT`
- 대사 지표: `triglyceride`, `BLDS`, `HDL_chole`, `LDL_chole`
- 혈압: `SBP`, `DBP`
- 혈액 지표: `hemoglobin`
- 기타: `serum_creatinine`

---

## 🔎 분석 내용

- 음주(`DRK_YN`) 및 흡연(`SMK_stat_type_cd`)과  
  각 건강 지표 간 **Pearson 상관관계 분석**
- 상관계수 절댓값 기준 정렬을 통해  
  **생활습관과 가장 연관성이 높은 지표 선별**
- 단순 평균 비교가 아닌  
  **연관성 크기 중심의 변수 중요도 판단**

---

## 📈 주요 결과

### 📊 음주(DRK_YN)와의 상관관계 TOP 지표

| 지표 | 상관계수 |
|---|---|
| SMK_stat_type_cd | 0.3508 |
| hemoglobin | 0.2993 |
| gamma_GTP | 0.2051 |
| triglyceride | 0.1044 |
| DBP | 0.1009 |

- 음주는 간 기능(gamma-GTP)뿐 아니라  
  **혈액 농도(hemoglobin)**, **대사 지표**, **혈압**과도 연관성을 보임

---

### 📊 흡연(SMK_stat_type_cd)과의 상관관계 TOP 지표

| 지표 | 상관계수 |
|---|---|
| hemoglobin | 0.4534 |
| DRK_YN | 0.3508 |
| gamma_GTP | 0.2436 |
| triglyceride | 0.2160 |
| HDL_chole | 0.1610 |

- 흡연의 경우 **hemoglobin과의 상관관계가 가장 높게 나타남**
- 이는 흡연으로 인한 만성 저산소 상태에 대한  
  **생리적 보상 반응**으로 해석 가능

---

## 💡 주요 인사이트

- 음주 및 흡연과 가장 높은 연관성을 보인 지표는  
  **hemoglobin, gamma-GTP, triglyceride**로 나타남
- gamma-GTP는 음주·흡연에 민감한 대표적 간 기능 지표이지만,  
  **흡연의 경우 hemoglobin이 가장 강한 연관성을 보임**
- 생활습관은 단일 장기에 국한되지 않고  
  **혈액, 간, 대사, 혈압 등 전신적인 건강 지표에 영향을 미침**
- 대규모 표본(약 99만 명)을 기반으로 하여  
  상관계수 값이 크지 않더라도 **통계적 신뢰도는 매우 높음**

---

## 🛠 사용 기술
- Python
- pandas, numpy
- matplotlib, seaborn
- scikit-learn
- Jupyter Notebook (Google Colab)

---

## 📌 참고 사항
- 본 프로젝트는 **개인 학습 및 분석 목적**으로 수행되었습니다.
- 상관관계 분석은 변수 간 연관성을 보여주며,  
  **인과관계를 의미하지는 않습니다.**
