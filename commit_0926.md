# [2022.09.26] 전처리 완료, 이상치 확인

* [credit_score] binning 변경
  지환님이 주신 자료 토대로 binning 구간을 변경했습니다!

* numerical value box plotting
  몇 개의 column에 존재하는 value에 대해서 논의가 필요할 것 같습니다
  
  - loan_limit == 1e10인 경우
  - yearly_income == 0인데 income_type이 정규직 (PERMANENT) 인 경우

------

<앞으로 수행해야 할 것>

1. QQPlot
   수치형 분포들이 어느 정도 정규 분포에 따르는지 확인

2. 베이스라인 모델 (트리 기반) 생성

3. Feature Engineering

4. feature 사이의 corr와 VIF factor 확인

5. 스케일링 - 파이프라인 구축

6. 다른 베이스라인 모델 실험

7. 하이퍼파라미터 최적화

8. 앙상블 방법 (스태킹, 보팅 등) 시도
