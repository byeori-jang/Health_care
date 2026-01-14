# ❤️ Heart Disease Prediction (개인 분석)

본 프로젝트는 심장질환(Heart Disease) 환자의 임상 검사 및 생활습관 데이터를 활용하여  
**심장질환 여부(Heart Disease)**를 예측하고,  
질환 발생에 영향을 미치는 주요 위험 요인을 분석한 개인 분석 프로젝트입니다.

분석 전 과정은 `heart_disease_analysis.ipynb` 노트북에 정리되어 있습니다.

---

## 🔍 분석 목적
- 심장질환 환자의 **질환 여부 예측**
- 심장질환에 영향을 미치는 **주요 임상 변수 도출**
- 해석 가능한 모델과 성능 중심 모델 비교

---

## 📂 파일 구성

| 파일명 | 설명 |
|---|---|
| `Heart_Disease_Prediction.csv` | 심장질환 환자 임상 데이터 |
| `heart_disease_analysis.ipynb` | EDA, 모델링, 시각화 전체 분석 노트북 |
| `README.md` | 프로젝트 설명 문서 |

---

## 📊 데이터 개요

- **Dataset**: Heart Disease Dataset  
- **표본 수**: 270명  
- **변수 수**: 13개 입력 변수 + 1개 타깃 변수  

### 🎯 타깃 변수
- `Heart Disease`
  - 0: Absence (심장질환 없음)
  - 1: Presence (심장질환 있음)

---

## 🧾 주요 변수

| 변수명 | 설명 |
|---|---|
| Age | 나이 |
| Sex | 성별 (1: 남성, 0: 여성) |
| Chest pain type | 흉통 유형 |
| BP | 안정 시 혈압 (mmHg) |
| Cholesterol | 혈중 콜레스테롤 |
| FBS over 120 | 공복 혈당 120 초과 여부 (0/1) |
| EKG results | 안정 시 심전도 결과 |
| Max HR | 최대 심박수 |
| Exercise angina | 운동 유발 협심증 여부 (0/1) |
| ST depression | 운동 후 ST 분절 하강 정도 |
| Slope of ST | ST 분절 기울기 |
| Number of vessels fluro | 조영술로 확인된 주요 혈관 수 |
| Thallium | 탈륨 스트레스 검사 결과 |

---

## 🔎 분석 내용

- 심장질환 유무에 따른 클래스 비율 확인  
  (큰 클래스 불균형 없음)
- 연속형 변수:
  - 박스플롯을 통한 질환군 vs 비질환군 분포 비교
- 범주형 변수:
  - countplot을 통한 질환 발생 비율 비교
- 변수 간 상관관계 분석
  - Heart Disease 기준 상관관계 시각화

---

## 🤖 모델링

- **Logistic Regression**
  - 해석 가능한 기준 모델
  - coef를 통한 심장질환 위험 증가/감소 방향 해석
- **RandomForest Classifier**
  - 비선형 관계를 고려한 성능 중심 모델
  - Feature Importance 기반 중요 변수 도출

---

## 📈 주요 인사이트

- 심장질환 환자에서 다음 변수들이 뚜렷한 차이를 보임
  - `Number of vessels fluro` 증가
  - `ST depression` 증가
  - `Exercise angina` 발생
  - `Max HR` 감소

- RandomForest 모델이 전반적으로 더 높은 또는 유사한 예측 성능을 보였으며  
  특히 **심장질환 환자 탐지(Recall)** 측면에서 안정적인 성능을 확인함

- Logistic Regression은 성능은 다소 낮지만  
  모델 해석이 가능하다는 장점이 있음

- 의료 데이터 특성상  
  **심장질환 환자를 정상으로 잘못 분류하는 것이 가장 위험**하므로  
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

