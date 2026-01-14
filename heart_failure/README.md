# ❤️ Heart Failure Survival Prediction (개인 분석)

본 프로젝트는 심부전(Heart Failure) 환자의 임상 및 생활습관 데이터를 활용하여  
**사망 여부(DEATH_EVENT)**를 예측하고,  
사망 위험에 영향을 미치는 주요 요인을 분석한 개인 분석 프로젝트입니다.

분석 전 과정은 `heart_failure_analysis.ipynb` 노트북에 정리되어 있습니다.

---

## 🔍 분석 목적
- 심부전 환자의 **사망 여부 예측**
- 사망에 영향을 미치는 **주요 임상 변수 도출**
- 해석 가능한 모델과 성능 중심 모델 비교

---

## 📂 파일 구성

| 파일명 | 설명 |
|---|---|
| `heart_failure.csv` | 심부전 환자 임상 데이터 |
| `heart_failure_analysis.ipynb` | EDA, 모델링, 시각화 전체 분석 노트북 |
| `README.md` | 프로젝트 설명 문서 |

---

## 📊 데이터 개요

- **Dataset**: Heart Failure Clinical Records Dataset  
- **표본 수**: 299명  
- **변수 수**: 12개 입력 변수 + 1개 타깃 변수  

### 🎯 타깃 변수
- `DEATH_EVENT`
  - 0: 생존
  - 1: 사망

---

## 🧾 주요 변수

| 변수명 | 설명 |
|---|---|
| age | 나이 |
| anaemia | 빈혈 여부 (0/1) |
| diabetes | 당뇨병 여부 (0/1) |
| high_blood_pressure | 고혈압 여부 (0/1) |
| ejection_fraction | 좌심실 박출률 (%) |
| serum_creatinine | 혈청 크레아티닌 |
| serum_sodium | 혈청 나트륨 |
| platelets | 혈소판 수 |
| smoking | 흡연 여부 (0/1) |
| time | 추적 관찰 기간 (일) |

---

## 🔎 분석 내용

- 사망 / 생존 비율 확인 (클래스 불균형 존재)
- 연속형 변수:
  - 박스플롯을 통한 사망군 vs 생존군 분포 비교
- 이진 변수:
  - countplot을 통한 사망 비율 비교
- 변수 간 상관관계 히트맵 시각화

---

## 🤖 모델링

- **Logistic Regression**
  - 해석 가능한 기준 모델
  - coef를 통한 사망 위험 증가/감소 방향 해석
- **RandomForest Classifier**
  - 비선형 관계를 고려한 성능 중심 모델
  - Feature Importance 기반 중요 변수 도출

---

## 📈 주요 인사이트

- 사망 환자에서 다음 변수들이 뚜렷한 차이를 보임
  - `ejection_fraction` 감소
  - `serum_creatinine` 증가
  - `age` 증가
  - `time` 감소 (조기 사망 환자일수록 관찰 기간이 짧음)

- RandomForest 모델이 전반적으로 더 높은 예측 성능을 보였으며  
  특히 **사망 환자 탐지(Recall)** 측면에서 우수함

- Logistic Regression은 성능은 다소 낮지만  
  모델 해석이 가능하다는 장점이 있음

- 의료 데이터 특성상  
  **사망 환자를 생존으로 잘못 분류하는 것이 가장 위험**하므로  
  Accuracy보다 **Recall 중심 평가**가 중요함

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
- 실제 의료 의사결정에는 의료 전문가의 판단이 필요합니다.
