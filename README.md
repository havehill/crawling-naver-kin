### 크롤링 코드 원출처
: https://github.com/catSirup/naver_kin_crawling

### 수정 사항 
0. **selenium 버전 업데이트로 인해 변경된 명령어 수정**
  - driver.find_elements_by_class_name => driver.find_elements(By.CLASS_NAME,)
1. **keyword 검색이 아닌 네이버 수의학 전문가 답변 크롤링**
  - crawling_expert_list : 수의학 전문가들 qna 사이트 url 크롤링
  - crawling_expert : expert_list로 얻은 url에 대해 모든 전문가들의 답변 페이지 url 크롤링
  - crawling_qna : crawling_expert 로 얻은 url에 대해 제목,본문,답변 크롤링
2. **빠르고 반복적인 크롤링으로 인해 생기는 Exception 처리**
  - find_element 문마다 try-except, WebDriverWait().until() 추가
3. **openpyxl를 사용할 때 크롤링 데이터 적재에 오류가 생기는 것을 확인하여 csv파일로 저장하도록 수정**
4. **답변이 2개 이상 달렸을 시 수의사 답변만 크롤링하도록 수정**
5. **수의사 답변이 2개 이상일 시,  "@Excepiton 수의사 답변이 2개 이상입니다."라는 문장을 답변 목록에 함께 저장하도록 함**
6. **웹에서 실시간으로 csv파일 적재 상태를 보기 위해 url 추가**
