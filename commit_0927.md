[2022.09.27] 전처리 완성 - 베이스라인 모델 (RandomForest)

* 빅콘 공지에 올라온대로 KCB 기준으로 신용등급 나눔

* 1차 전처리 과정에서 진행하지 못했던 스케일링 & 가변수 처리 완료
  
  - 스케일링 : StandardScaler
  - 카테고리형 변수 OneHotEncoder(sparse=False)

* StratifiedShuffleSplit을 통한 계층적 샘플링
  
  train - validation set으로 나눠 train으로 학습 후 validation으로 검증

* 모델 성능 측정
  
  * accuracy_score : 타깃이 불균형해서 크게 도움은 되지 않지만.. 궁금해서 한 번 넣어봤습니다
  * precision
  * recall
  * **f1 score** : 대회 성능 평가 지표
  * auc score
  * roc curve plotting
  
  -> save_data 함수를 통해 성능 평가표 저장 (in score folder)

* 분류기가 학습한 내용에서 importances 중요도 뽑아서 데이터프레임화
  
  -> save_data 함수를 통해 변수별 중요도표 저장 (in score folder)

\<StandardScaler 사용\>

* train score
  
  accuracy : 0.989766684745195, precision : 0.9590964098426785, recall : 0.8486332983097202, f1 score : 0.9004898752410023

* valid score
  
  accuracy : 0.9428360133845959, precision : 0.4417784358125762, recall : 0.1810524061498925, f1 score : 0.2568435709990823
  
  valid score에서 precision과 recall이 크게 떨어졌고, 그에 따라 f1 score도 낮게 나온것을 확인할 수 있었습니다

* valid ROC AUC score
  
  0.8915601033661048

data : train_prepared.csv, target_prepared.csv

model : baseline_rf_model.pkl

---

- train에서의 과적합으로 인한 문제라고 추정, 다음 커밋에서는 StandardScaling을 하지 않은 상태로 모델을 다시 돌려볼 예정
- train에서의 평균, 표준편차와 valid에서의 평균, 표준편차가 달라서 생기는 문제인지 확인해봐야함

----

\<StandardScaler 미사용\>

* train score
  
  accuracy : 0.9896803897951414, precision : 0.9589744755324227, recall : 0.8470985055848163, f1 score : 0.8995714498923295
  
  train ROC AUC score : 0.9977725177165484

* valid score
  
  accuracy : 0.9428033941527836, precision : 0.4406419222590051, recall : 0.17934806856612562, f1 score : 0.25493404363267375
  
  valid ROC AUC score : 0.8907858383547306

data : train_prepared_nonstandard.csv, target_prepared_nonstandard.csv

model : baseline_rf2_model.pkl

-----

크게 다르지는 않지만 정규화를 하지 않았을 경우 오히려 score가 떨어짐.

1. train, valid의 분포 확인 후 스케일링 재진행

2. randomforest 이외의 다른 모델 점수 확인

-----

<0926 회의 내용>

* Imbalanced target 처리방법 논의

* Feature Engineering
  
  * 날짜에 따른 경제지표나 사회적 지표 추가 논의
  
  * 내부 변수에서 특성공학 다룰 것은 없는지 다시 살펴보기
