# ❤️ Heart Failure Survival Prediction

본 프로젝트는 심부전(Heart Failure) 환자의 임상 및 생활습관 데이터를 활용하여  
**사망 여부(DEATH_EVENT)**를 예측하는 머신러닝 모델을 구축하고,  
모델 결과를 시각화 및 해석하여 사망 위험 요인을 분석하는 것을 목표로 합니다.

본 저장소의 분석 내용은 `heart_failure_analysis.ipynb` 노트북에 모두 포함되어 있습니다.

---

## 📁 Folder Structure

```text
heart-failure-prediction/
├── heart_failure.csv
├── heart_failure_analysis.ipynb
└── README.md
```
📊 Dataset Information
Dataset: Heart Failure Clinical Records Dataset

Samples: 299 patients

Features: 12 input features + 1 target

🎯 Target Variable
DEATH_EVENT

0 : 생존

1 : 사망

🧾 Feature Description
변수명	설명
age	나이
anaemia	빈혈 여부 (0/1)
diabetes	당뇨병 여부 (0/1)
high_blood_pressure	고혈압 여부 (0/1)
ejection_fraction	좌심실 박출률 (%)
serum_creatinine	혈청 크레아티닌
serum_sodium	혈청 나트륨
platelets	혈소판 수
smoking	흡연 여부 (0/1)
time	추적 관찰 기간 (일)

🔎 Analysis Workflow (Notebook 기준)
1️⃣ Environment & Setup
Google Colab 환경 사용

Google Drive 마운트 후 데이터 로드

한글 시각화를 위한 NanumGothic 폰트 설치 및 matplotlib 설정

2️⃣ Exploratory Data Analysis (EDA)
DEATH_EVENT 분포 확인 → 사망/생존 클래스 불균형 존재

연속형 변수: 박스플롯을 통한 사망군 vs 생존군 분포 비교

이진 변수: countplot을 활용한 사망 비율 비교

변수 간 상관관계 히트맵 시각화

3️⃣ Data Preprocessing
입력 변수(X) / 타깃(y) 분리

Train / Test 데이터 분리 (stratify 적용)

로지스틱 회귀를 위한 표준화(Standard Scaling)

4️⃣ Modeling
Logistic Regression

해석 가능한 기준 모델

coef를 통한 변수 영향 분석

RandomForest Classifier

성능 중심 모델

Feature Importance 기반 중요 변수 도출

5️⃣ Evaluation & Visualization
Accuracy, Precision, Recall, F1-score

Confusion Matrix 시각화

ROC Curve 및 AUC 비교

주요 변수 시각화 (coef / importance)

📈 Key Insights
사망 환자에서 다음 변수들이 뚜렷한 차이를 보임

ejection_fraction 감소

serum_creatinine 증가

age 증가

time 감소 (조기 사망 환자일수록 관찰 기간이 짧음)

RandomForest 모델이 전반적으로 더 높은 예측 성능을 보였으며
특히 사망 환자 탐지(Recall) 측면에서 우수함

Logistic Regression은 성능은 다소 낮지만
사망 위험 증가/감소 방향을 해석할 수 있다는 장점이 있음

의료 데이터 특성상
사망 환자를 생존으로 잘못 분류하는 것이 가장 위험하므로
Accuracy보다 Recall 중심 평가가 중요함

🛠️ Libraries & Environment
Python 3.x

pandas, numpy

matplotlib, seaborn

scikit-learn

Google Colab

