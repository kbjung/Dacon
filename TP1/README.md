# 🤝🏼 팀프로젝트1 [상세내용](https://github.com/kbjung/Dacon/tree/main/TP1)
## 주식 종료 가격 예측 경진대회
+ 대회 [대회 링크](https://dacon.io/competitions/official/235857/overview/description)
+ 목표 : 데이터 전처리, 분석, 머신러닝 활용 기술 향상
+ 주제 : KOSPI-200과 KOSDAQ-150의 주어진 기간에 마지막으로 거래된 가격(종가)를 예측
+ 기간 : 2021.11.10 ~  2021.11.29 10:00 am
  - 팀 병합 마감 : 2021. 11. 26
  - private score 공개 : 2021. 12. 03
  - 코드 제출 마감 : 2021. 12. 08
  - 발표자료 제출 마감 : 2021. 12. 08
  - 코드 및 발표자료 평가 : 2021. 12. 14
  - 최종 결과 발표 : 2021. 12. 15
+ 대회 배경
  - 코로나19 대유행으로 변동성이 높아져 주식 투자에 관심이 많습니다. -중략- 주식의 종료 가격을 정확하게 예측할 수 있다면 어떨까요?
+ 평가(Public, Private score)
  - public score: 11월 1일 ~ 11월 5일 주식 종료 예측값
  - private score: 11월 29일 ~ 12월 3일 주식 종료 예측값
+ 예측 타겟
  - 11.01 ~ 11.05 종목 별 주가(월~금)
  - 11.29 ~ 12.03 종목 별 주가(월~금)
+ 활용 기술 🔧
  - 데이터 수집 : pandas, financedatareader
  - 데이터 탐색 : seaborn, matplotlib
+ 역할
  - 팀장 : 최두호
  - 팀원 : 김범중 📢, 김진연

### 전략
  + 다양한 데이터 수집과 머신러닝을 통한 주가 예측


### 01 데이터 수집 [폴더](https://github.com/kbjung/Dacon/tree/main/TP1/01_%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%88%98%EC%A7%91)
  + 데이터 수집(2021.11.22) [code(html)](https://kbjung.github.io/Dacon/TP1/01_데이터수집/01-01_데이터_수집_주가.html)
  + 데이터 종합(2021.11.22) [code(html)](https://kbjung.github.io/Dacon/TP1/01_데이터수집/01-02_데이터_수집_합치기.html)
  + 데이터 결측치 처리(2021.11.22) [code(html)](https://kbjung.github.io/Dacon/TP1/01_데이터수집/01-03_결측치_처리.html)


### 02 데이터 분석 [폴더](https://github.com/kbjung/Dacon/tree/main/TP1/02_%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B6%84%EC%84%9D)
  + 데이터 탐색(2021.11.22) [code(html)](https://kbjung.github.io/Dacon/TP1/02_데이터분석/02-01_EDA.html)
