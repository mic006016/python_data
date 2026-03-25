## Titanic Survival Prediction: Ensemble Learning

이 프로젝트는 타이타닉 데이터셋을 활용하여 승객의 생존 여부를 예측하는 모델을 구축하며, 앙상블 학습의 대표적인 기법인 **Stacking**과 **Bagging**을 실습합니다.

### 1. 사용 기술 및 환경

- **Language**: Python 3.x
- **Libraries**: scikit-learn, pandas
- **Dataset**: OpenML Titanic dataset

### 2. 데이터 전처리

- **특징 선택**: `pclass`, `sex`, `age`, `fare`
- **결측치 처리**: 데이터가 없는 행(null)은 삭제
- **데이터 인코딩**: 성별(`sex`) 데이터를 수치형(`male: 0`, `female: 1`)으로 변환

### 3. 모델링 및 성능

#### 스태킹 (Stacking)

여러 모델의 예측 결과를 다시 최종 모델의 입력값으로 사용하는 기법입니다.

- **기본 모델 (Base Models)**: Logistic Regression, Decision Tree, SVC
- **최종 모델 (Final Estimator)**: Gradient Boosting Classifier
- **결과**: 약 79.4%의 정확도 기록

#### 배깅 (Bagging) - 랜덤 포레스트

여러 개의 결정 트리를 독립적으로 학습시켜 결과를 집계하는 기법입니다.

- **모델**: RandomForestClassifier
- **결과**: 약 81.3%의 정확도 기록
