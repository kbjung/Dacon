# 🤝🏼 팀프로젝트1 [[상세내용]](https://github.com/kbjung/Dacon/tree/main/TP1)
## 주식 종료 가격 예측 경진대회(종료)
+ 대회 [[대회 링크]](https://dacon.io/competitions/official/235857/overview/description)
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
  - 머신 러닝 모델 및 라이브러리 : Pycaret, LinearRegression, Ridge, Catboost 등
  - 평가지표 : MSE, RMSE, R2, NMAE(대회점수지표), NMAE*100(대회점수지표)
+ 역할
  - 팀명 : 작전주사냥꾼
  - 팀장 : 최두호
  - 팀원 : 김범중 📢, 김진연

### 전략
  + 다양한 데이터 수집과 머신러닝을 통한 주가 예측
    - 외부자료 : KOSDAQ, KOSPI, DOW, NASDAQ, S&P500, 환율, 금, 유가, 비트코인, 미국 국채 10년, 미국 국채2년
    - 외부자료 중 종가와 상관관계가 높은 자료만 선정(KOSDAQ, KOSPI, DOW, NASDAQ, S&P500)


#### 세부 분석 아이디어
  + 타겟 날짜의 주가 인덱스를 상관계수가 높은 순으로 예측한 뒤, 마지막으로 종목 별로 종가 예측.
    - 정확도는 좋은 편이나 시간이 오래 걸리는 문제 발생(최대 8시간)
    - 과정이 복잡하여 코드 작성에 많은 시간 할애. 오류 발생 확률 상승.
    - 오류 발생 지점 파악 어려움
  + 지수 데이터에 종목 코드를 열로 붙여, 하나의 데이터 셋으로 만들어 종가 예측.(최두호님 아이디어)
    - 한 번의 훈련으로 모든 종목 예측 가능. 시간이 많이 단축됨(최대 3시간. 평균적으로 1시간 반정도)
    - 정확도가 낮음.
    - 종목 코드를 카테고리형으로 지정시 진행 시간 많이 늘어남.
    - 종목별로 종가 값이 거의 유사. weeknum이 같으면 값이 종가가 같은 문제 발생
  + KOSPI, KOSDAQ 별로 종목 나누어 예측
    - 한 종목씩 예측하니 시간 오래 걸리고, 결과가 별로 개선되지않음.
  + stationary하게 데이터 변환
    - 5가지 지수와 종가 데이터를 비율로 변환(전날 기준으로 얼마나 변화했는지)
    - 전체 종목에 대해 한번에 비율로 훈련, 다시 원래 값으로 변환
    - 점수 향상. 자체점수 : 3.22868 ✨


### 01 데이터 수집 [[폴더]](https://github.com/kbjung/Dacon/tree/main/TP1/01_%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%88%98%EC%A7%91)
  + 데이터 수집
    - 2021.01.04-11.19 / KOSPI, KOSDAQ, NASDAQ, DOW, S&P500, 금, 원유, 환율, 미국 국채 2, 10년, 비트코인 (2021.11.22) [code(html)](https://kbjung.github.io/Dacon/TP1/01_데이터수집/01-01_주식지수_데이터_수집_ver0.1.html)
    - 2021.01.04-11.26 / KOSDAQ, NASDAQ, DOW, S&P500, KOSPI (2021.11.29) [code(html)](https://kbjung.github.io/Dacon/TP1/01_데이터수집/01-01_주식지수_데이터_수집_ver0.2.html)
  + 데이터 종합(2021.11.22) [code(html)](https://kbjung.github.io/Dacon/TP1/01_데이터수집/01-02_데이터_수집_합치기.html)
  + 데이터 결측치 처리(2021.11.22) [code(html)](https://kbjung.github.io/Dacon/TP1/01_데이터수집/01-03_결측치_처리.html)
  + 주식 종가 수집(2021.11.26) [code(html](https://kbjung.github.io/Dacon/TP1/01_데이터수집/01-04_종목_종가_수집.html)
  + 주식 지수, 종목 코드, 종가 수집(2021.11.29) [code(html)](https://kbjung.github.io/Dacon/TP1/01_데이터수집/01-05_주식지수_종목코드_셋_ver0.1.html)
  + 주식 지수, 종가를 전날 기준 변화 비율로 변환한 값 추가(stationary) [code(html)](https://kbjung.github.io/Dacon/TP1/01_데이터수집/01-06_주가_비율_셋_ver0.1.html)


### 02 데이터 분석 [[폴더]](https://github.com/kbjung/Dacon/tree/main/TP1/02_%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B6%84%EC%84%9D)
  + 데이터 탐색(2021.11.22) [code(html)](https://kbjung.github.io/Dacon/TP1/02_데이터분석/02-01_EDA.html)
  + 데이터 탐색(KOSPI, KOSDAQ, TOTAL 평균 상관계수)(2021.11.26) [code(html)](https://kbjung.github.io/Dacon/TP1/02_데이터분석/02-02_EDA.html)

### 03 모델 선정 [[폴더]](https://github.com/kbjung/Dacon/tree/main/TP1/03_%EB%AA%A8%EB%8D%B8_%EC%84%A0%EC%A0%95)
  + catboost 모델로 각 단계 예측으로 진행 ver0.4 [code(html)](https://kbjung.github.io/Dacon/TP1/03_모델_선정/03-01_모델_선정_ver0.4.html)
    - 1주 복제해서 제출
    - 1번째 제출 파일
    - 자체점수 : 4.09278
  + pycaret으로 top1 모델로 진행 ver0.8(2021.11.25) [code(html)](https://kbjung.github.io/Dacon/TP1/03_모델_선정/03-01_모델_선정_ver0.8.html)
    - 4주 훈련, 1주 예측(2개)
    - 한 종목씩 예측
    - 2번째 제출 파일
    - 자체점수 : 6.26797
  + pycaret으로 top1 모델로 진행 ver0.9(2021.11.25) [code(html)](https://kbjung.github.io/Dacon/TP1/03_모델_선정/03-01_모델_선정_ver0.9.html)
    - 4주 훈련, 1주 예측(2개)
    - all_훈련, all_테스트 셋 csv 파일(2개)로 생성
    - 각 훈련 모델(2개) 저장
    - 3번째 제출 파일
    - 자체점수 : 309.87425
  + pycaret, top1 모델 ver1.0(colab)(2021.11.26) [code(html)](https://kbjung.github.io/Dacon/TP1/03_모델_선정/03-01_모델_선정_ver1.0(colab).html)
    - 4주 훈련, 1주 예측(2개)
    - 종목코드를 카테고리형으로 설정, weeknum 제외
    - 각 훈련 모델(2개) 저장
    - 자체점수 : 140.8549
  + pycaret, top1 모델 ver1.0.1(colab)(2021.11.26) [code(html)](https://kbjung.github.io/Dacon/TP1/03_모델_선정/03-01_모델_선정_ver1.0.1(colab).html)
    - 모델 튜닝만 제외, 나머지 조건 ver1.0과 동일
    - 4번째 제출 파일
    - 자체점수 : 6.31279
  + pycaret, top1 모델 ver1.1(2021.11.26) [code(html)](https://kbjung.github.io/Dacon/TP1/03_모델_선정/03-01_모델_선정_ver1.1.html)
    - 한 종목씩 예측
    - 튜닝 제외
    - 5번째 제출 파일(미제출)
    - 자체점수 : 5.72819
  + pycaret, top1 모델 ver0.1(2021.11.28) [code(html)](https://kbjung.github.io/Dacon/TP1/03_모델_선정/03-02_pycaret_ver0.1.html)
    - 예측 날 전날 데이터까지 사용
    - 튜닝 제외
    - 자체점수 : 4.27195
  + pycaret, ridge 모델 ver0.1(2021.11.29) [code(html)](https://kbjung.github.io/Dacon/TP1/03_모델_선정/03-02_pycaret_ridge_ver0.1.html)
    - 자체점수 : 3.91912
  + pycaret, catboost 모델 ver0.1(2021.11.29) [code(html)](https://kbjung.github.io/Dacon/TP1/03_모델_선정/03-02_pycaret_catboost_ver0.1.html)
    - 한 종목씩 예측
    - 자체점수 : 4.09893
  + pycaret, catboost 모델 ver0.2(2021.11.29) [code(html)](https://kbjung.github.io/Dacon/TP1/03_모델_선정/03-02_pycaret_catboost_ver0.2.html)
    - KOSPI, KOSDAQ 종목 별 예측
    - pivot table 생성
    - multi level columns에서 특정 column 만 제거
  + pycaret, catboost 모델, 비율 예측 ver0.1(2021.11.30) [code(html)](https://kbjung.github.io/Dacon/TP1/03_모델_선정/03-03_pycaret_cat_rate_ver0.1.html)
    - KOPDAQ, NASDAQ, DOW, S&P500, KOSPI, 종가 비율 이용
    - 모든 종목 포함한 데이터 셋
    - 지수 비율을 하루 씩 예측
    - 종가 비율 예측 시 KOSPI, KOSDAQ 종목 별로 예측
    - 자체 점수 : 2.00692 (코드 알고리즘 문제. 11-02~05일 데이터 유출)
  + pycaret, catboost 모델, 비율 예측 ver0.2(2021.12.01) [code(html)](https://kbjung.github.io/Dacon/TP1/03_모델_선정/03-03_pycaret_cat_rate_ver0.2.html)
    - 자체 점수 : 3.22868 ✨

### 04 평가지표 [[폴더]](https://github.com/kbjung/Dacon/tree/main/TP1/04_%ED%8F%89%EA%B0%80%EC%A7%80%ED%91%9C)
  + 회귀 평가지표 함수화 ver0.3(2021.11.26) [code(html)](https://kbjung.github.io/Dacon/TP1/04_평가지표/04-01_평가지표_ver0.3.html)

### 제출 점수
특성 2개 : weekday, weeknum  
특성 3개 : Date, weekday, weeknum  
특성 5개 : KOSDAQ, NASDAQ, S&P500, DOW, KOSPI  
|번호|제출일시|제출점수|자체점수|모델&알고리즘|특성, 방법|
|---|---|---|---|---|---|
|00|2021-11-22 09:36:01|3.4608244253|3.56289|linearregression(baseline)|1주전 , 1주 복제|
|01|2021-11-23 17:57:45|3.9881899683|4.09278|catboost|2+5, 각 단계별 예측, 1주 복제|
|02|2021-11-25 16:23:33|6.3488498272|6.26797|pycaret(top1)|3+5, 각 단계별 예측, 4주 훈련|
|03|2021-11-26 11:32:28|309.6832896345|309.87425|pycaret(top1)|동일, 훈련셋에 종목코드 붙여 전체 종목 한번에 훈련, weeknum제외, 종목코드->카테고리형|
|04|2021-11-26 12:13:21|6.3924548775|6.31279|pycaret(top1)|03과 동일, 모델 튜닝 제외|
|05|2021.11.26|-|5.72819|pycaret(top1)|한 종목씩 예측, 모델 튜닝 제외|
|06|2021.11.28|-|4.27195|pycaret(top1)|바로 전날 데이터까지 사용, 한 종목씩 예측, 모델 튜닝 제외|
|07|2021.11.29|-|3.91912|pycaret(ridge)|바로 전날 데이터까지 사용, 한 종목씩 예측, 모델 튜닝 제외|
|08|2021.11.29|-|4.09893|pycaret(catboost)|바로 전날 데이터까지 사용, 한 종목씩 예측, 모델 튜닝 제외|
|09|2021.11.30|-|2.00692(오류)|pycaret(catboost)|비율로 예측, 바로 전날 데이터까지 사용, 한 종목씩 예측, 모델 튜닝 제외|
|10|2021.12.01|-|3.22868✨|pycaret(catboost)|비율로 예측, 바로 전날 데이터까지 사용, 한 종목씩 예측, 모델 튜닝 제외|
