[2022.09.20] Baseline - 간단한 전처리 후 결측치 제거 및 확인


* merge_train만 NaN 값인 columns 의 결측치 제거
	- user_id 가 NaN 값인 경우 다른 피쳐도 NaN 인 경우가 많았다.
	- user_id 가 NaN 인 행을 삭제하는 방법으로 결측치 제거
	- 결과 : merge_train만 NaN 값인 columns 의 결측치 문제 해결

* 결측치 filling 방법에 대해 생각 해봐야할 column
	- 우선 결측치를 처리 전 처리 방법을 주석으로 설명
	- loan_rate : 승인한도 -->  loan_rate 와 loan_limit 가 NaN 값이면 모두 is_appiled 가 1이라서
	  논의 필요
	- credit_score --> 신용 점수의 경우 0으로 채워넣기
	- company_enter_month  : 입사 연월 --> 입사 연월에 경우 데이터를 입사연월로 부터 지금까지 일한 개월 수 
	즉 일한 경력(개월 단위) 로 전환하여 입사연월이 NaN 인 경우 0으로 채워놓으면 좋을 것 같습니다.
	- personal_rehabilitation_yn : 개인회생자여부 personal_rehabilitation_complete_yn : 개인회생자납입완료여부
	  0, 1, 알수없음 등으로 3개의 카테코리로 나누면 좋을 것 같습니다.
	- existing_loan_cnt : 대출의 목적과 기존 대출의 금액을 확인하여 채워넣고 그 나머지는 0 과 같은 값으로 채워
	넣어야할 것 같습니다.
