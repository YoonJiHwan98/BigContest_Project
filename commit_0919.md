[2022.09.19] Baseline - EDA 및 간단한 전처리

* loan_result, user_spec 'application id' 기준 left merge를 진행

* NaN값인 것은 예측해야할 target data로 분리

* 'purpose' column에서 영문/한글 value가 혼재되어있음을 확인, 한글 value를 영문으로 변환

* 카테고리형 변수 시각화

* 수치형 변수 시각화 (진행중)

----

* 설명회 영상을 살펴보니 회귀 예측 모델 / 군집화로 문제가 나눠져있더라구요!
  회귀 문제에는 우선 user_spec, loan_result 데이터를 사용해보고 군집화문제에 log_data를 추가적으로 사용하는 방법을 생각해봤습니다

* 아무래도 타깃 불균형이 심하다보니 이걸 해결할 수 있는 방법도 찾아야 할 것 같습니다

* 변수들 간의 관계를 좀 더 분석해 가설을 세운 후 피처 엔지니어링을 진행할 예정입니다

* 'credit_score'가 극단적으로 낮은 경우가 몇 개 눈에 띄었는데, 이는 'personal_rehabilitation' 과 큰 관련이 있을 것으로 보입니다 -> 세 변수간의 상관관계를 시각화해보고, 일반 고객들과는 다른 방식으로 처리할 수 있게 하면 좋을 듯 합니다! 

