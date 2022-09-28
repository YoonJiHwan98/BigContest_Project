[2022.09.28] 베이스라인 모델 (SVC-Bagging)

스케일링 : StandardScaler
카테고리형 변수 OneHotEncoder(sparse=False)

train - validation set으로 나눠 train으로 학습 후 validation으로 검증

모델 성능 측정

accuracy_score
precision
recall
f1 score : 대회 성능 평가 지표
auc score

-> save_data 함수를 통해 변수별 중요도표 저장 (in score folder)

<StandardScaler 사용>

train score

accuracy : 0.9455244596567154, precision : 0.20784313725490197, recall : 0.00016924742376680897, f1 score : 0.00033821943421632

valid score

accuracy : 0.9453666081977908, precision : 0.2602739726027397, recall : 0.0002419858119897602, f1 score : 0.0004835220766000764

valid score에서 precision과 recall, f1 score 가 떨어졌지만 크게 떨어지지않은 것 같습니다.


data : train_prepared.csv, target_prepared.csv

model : svc_model.pkl
