[2022.09.23] user_spec, loan_reslut 데이터 전처리

1. user_spec

  1-1 'gender', 'income_type','employment_type','houseown_type','desired_amount','purpose'
    NORESPONSE 로 카테고리 추가
  1-2 birth_year
    평균값으로 filling
  1-3 Credit score
    나이스 신용점수를 기반으로 신용등급으로 나눔, 결측치는 0으로 filling
  1-4 yearly_income, existing_loan_cnt, existing_loan_amt
    0으로 filling
  1-5 company_enter_month
    예원님 사용하신 함수.. 참고하였습니다... 뭐가 너무 안되서.. ㅠㅠ
    
2. loan_result
  2-1 loan_limit, loan_rate
    중앙값으로 filling
