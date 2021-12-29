## 🤝🏼 팀프로젝트2(진행 중...) [[상세내용]](https://github.com/kbjung/Dacon/tree/main/TP2(잡케어))
+ 대회 : 잡케어 추천 알고리즘 경진대회 [[대회 링크]](https://dacon.io/competitions/official/235863/overview/description)
+ 목표 : 데이터 전처리, 분석, 머신러닝 활용 기술 향상
+ 주제 : 구직자의 이력서를 인공지능 기술로 직무역량을 자동 분석하여 개인별 맞춤형 컨텐츠 추천 모델 구축
+ 기간 : 2021년 12월 6일 (19:00) ~ 2022년 1월 28일
+ 팀원 : 최두호(팀장), 김범중, 김진연
+ 활용 기술 🔧
  - 데이터 수집 : 
  - 데이터 탐색 : matplotlib
  - 머신 러닝 모델 및 라이브러리 : pycaret(classification), randomforest, catboost, naive bayes
  - 평가지표 : F1-score(대회평가지표)
+ 점수 기록 : 스프레트시트 [[링크]](https://docs.google.com/spreadsheets/d/10Bz8g40J4Zkls3ohjEG3HL_vR_lth4rkqEX6XCwhgPM/edit#gid=0)
  - 최고점 : **✨0.6886392929**(2021-12-28 14:05:53, 71등,  총 549명 참가)


### 01 데이터 수집 [[폴더]](https://github.com/kbjung/Dacon/tree/main/TP2(%EC%9E%A1%EC%BC%80%EC%96%B4)/01_%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%88%98%EC%A7%91)
+ 기존 데이터 + 속성D코드, 속성H코드, 속성L코드 추가 [code](https://github.com/kbjung/Dacon/blob/main/TP2(%EC%9E%A1%EC%BC%80%EC%96%B4)/01_%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%88%98%EC%A7%91/01_01_%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%88%98%EC%A7%91_ver0.1.ipynb)

### 02 데이터 분석 [[폴더]](https://github.com/kbjung/Dacon/tree/main/TP2(%EC%9E%A1%EC%BC%80%EC%96%B4)/02_%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B6%84%EC%84%9D)
+ 기본 데이터 분석(2021.12.14 ~ 17) [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/02_데이터분석/02-01_분석ver0.1.html)
  - 속성별 target값 분포 확인
  - 사용자가 이용한 컨텐츠 수 파악한 뒤, 이용 컨텐츠 수별 target 값 비율 확인.(열람한 컨텐츠가 많을 수록 이용을 많이 할 것으로 가정)
  - target 값별로 데이터 셋을 만든 뒤, 각 셋에서 특성마다 유니크 값 개수의 분포를 비교.(특성1의 유니크 값 분포를 target 값이 0, 1일때 비교) 많은 차이가 나는 특성이 훈련/예측에 좋을 것이라 판단.
+ 매칭별 경우의 수로 분석(2021.12.21~25)
  - ver0.2 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/02_데이터분석/02-01_분석ver0.2.html)
  - ver0.3 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/02_데이터분석/02-01_분석ver0.3.html)
  - 매칭별로 나누어, target 값의 분포 확인.
+ target값 별 특성의 분포 확인(2021.12.29)
  - ver0.4 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/02_데이터분석/02-01_분석ver0.4.html)
  - 매칭 특성은 사람 선호 특성과 컨텐츠 속성이 같은지 다른지를 알려주기에, 비교되는 두 특성이 있다면 의미 없는 특성이라 판단.
  - 최대한 사용되는 특성을 줄이는 방향으로 진행.

### 03 모델 선정 및 개선 [[폴더]](https://github.com/kbjung/Dacon/tree/main/TP2(%EC%9E%A1%EC%BC%80%EC%96%B4)/03_%EB%AA%A8%EB%8D%B8%EC%84%A0%EC%A0%95%EB%B0%8F%EA%B0%9C%EC%84%A0)
+ 기본 테스트 (2021.12.14) [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver0.1.html)
  - ver0.1 : pycaret, cat / combine
  - ver0.1.1 : 모델 비교 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver0.1.1.html)
+ 10개 이상 컨텐츠 사용자 데이터로 예측(2021.12.14) [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver0.2.html)
  - ver0.2 : pycaret, rf / combine
+ 5개 이상 컨텐츠 사용자 데이터로 예측(2021.12.15)
  - ver0.3 : pycaret, nb / combine [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver0.3.html)
  - ver0.4 : pycaret, nb / combine, cardinality [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver0.4.html)
  - ver0.5 : pycaret, cat / combine [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver0.5.html)
+ 특정 특성 제거(2021.12.17)
  - 1값으로 채워진 person_prefer_f, g 특성 제거
  - ver0.6 : pycaret, cat, tune [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver0.6.html)
  - ver0.7 : pycaret, cat, tune / combine [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver0.7.html)
  - target값 기준, 특성별 유니크 값이 비교적 많이 다른 특성만 선택(22개)
  - ver0.8 : pycaret, cat / combine [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver0.8.html)
+ 1값으로 채워진 person_prefer_f, g 특성 제거, 순서형 특성 수치형 지정(2021.12.18)
  - ver0.9 : pycaret, cat / combine, numeric [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver0.9.html)
+ 기본2, f, g, 사용자 번호, 컨텐츠 번호 총 6개 특성 제거(2021.12.19)
  - ver1.0 : pycaret, nb / combine [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver1.0.html)
  - ver1.1 : pycaret, tuned_nb / combine [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver1.1.html)
  - 추가)순서형 특성 수치형 지정
  - ver1.2 : pycaret, nb / combine [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver1.2.html)
+ target값 기준, 특성별 유니크 값이 비교적 많이 다른 특성만 선택(22특성)(2021.12.20)
  - ver1.3 : pycaret, nb / combine, 순서형 -> 수치형 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver1.3.html)
+ target값 기준, 특성별 유니크 값이 비교적 많이 다른 특성만 선택(25특성)(2021.12.20)
  - ver1.4 : pycaret, nb / combine, 순서형->수치형 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver1.4.html)
  - ver1.5 : pycaret, cat / combine, 순서형->수치형 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver1.5.html)
+ 기본2특성 제거(2021.12.21)
  - ver1.6 : pycaret, cat / combine, 순서형->수치형 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver1.6.html)
+ 25특성, 8매칭별 훈련(2021.12.21)
  - ver1.7 : pycaret, nb / combine, 순서형->수치형 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver1.7.html)
+ 25특성, 8매칭별 훈련, blend(2021.12.22)
  - ver1.8 : pycaret, nb/cat / combine, 수치형 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver1.8.html)
+ 25특성, 8매칭별 훈련, 단계별 blend(2021.12.22)
  - ver1.9 : pycaret, blend 2 models(nb, cat, gbc, lr 중) / combine, 수치형 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver1.9.html)
  - ver2.0 : pycaret, blend 2 models(nb, cat, gbc 중) / combine, 수치형, minmax [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver2.0.html)
+ 25특성, 8매칭별 훈련, blend(2021.12.22)
  - ver2.1 : pycaret, blend 3 models(nb, cat, gbc) / combine, 수치형, minmax [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver2.1.html)
+ 25특성, 4매칭별 훈련, 단계별 blend(2021.12.25)
  - ver.2.2 : pycaret, blend 2 models(nb, cat, gbc 중) / combine, 수치형, minmax [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver2.2.html)
+ 5특성 제거, probability_threshold 제한(2021.12.27)
  - ver2.3 : pycaret, cat / combine, 수치형 / probability_threshold [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver2.3.html)
  - ver2.4 : pycaret, cat / combine, 수치형 / probability_threshold [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver2.4.html)
+ 26특성, probability_threshold 제한(2021.12.27)
  - ver2.5 : pycaret, cat / combine, 수치형 / probability_threshold [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver2.5.html)
+ 26특성, blend, probability_threshold(이하 pb_thr) 제한(2021.12.28)
  - ✨ver2.6 : pycaret(이하 py), blend(cat, tuned_lgbm) / combine(이하 comb), numeric(이하 nu) / probabiltily_threshold [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver2.6.html)
+ 속성데이터 추가(이하 data2), 5특성 제거, pb_thr 제한(2021.12.29)
  - ver2.7 : py:cat/comb,nu/pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver2.7.html)
