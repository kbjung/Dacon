## 🤝🏼 팀프로젝트2 [[상세내용]](https://github.com/kbjung/Dacon/tree/main/TP2(잡케어))

### 🏆 대회 정보
+ 대회 : 잡케어 추천 알고리즘 경진대회 [[대회 링크]](https://dacon.io/competitions/official/235863/overview/description)
+ 목표 : 데이터 전처리, 분석, 머신러닝 활용 기술 향상
+ 주제 : 구직자의 이력서를 인공지능 기술로 직무역량을 자동 분석하여 개인별 맞춤형 컨텐츠 추천 모델 구축
+ 기간 : 2021.12.06 19:00 ~ 2022.01.28

### 👨‍💻 팀정보
+ 팀명 : 보더 콜리
+ 팀원 : 김범중(팀장), 최두호, 김진연
+ 내용정리 : [[링크]](https://www.notion.so/Dacon-2d14915013594e6cb30ad36c34ff4c64)

### 🔧 활용 기술 
  - 데이터 수집 : pandas
  - 데이터 탐색 : matplotlib, numpy
  - 머신 러닝 모델 및 라이브러리 : pycaret(classification), randomforest, catboost, naive bayes
  - 평가지표 : F1-score(대회평가지표)
  
### 👏 성과
+ 점수 기록 : 스프레트시트 [[링크]](https://docs.google.com/spreadsheets/d/18vwewjISwsBQNSL2arV_i5q9LlNfJ-QEtrCiNTuGIJ4/edit?usp=sharing)
  - ✨ public 최고점 : **37등**(총 1,335명 참가) 기록(**0.701834167 점**, 2022-01-13 11:08:38)
  - ✨ private 최고점 : **189등**(총 1,335명 참가) 기록(**0.6997627581 점**)
+ 배운 점  
  - 적절한 특성 선택 필요. 많은 특성은 노이즈 발생시킴.
  - 기준 확률 조정이 효과가 높음.
  - 데이셋을 나누어 진행하는 것이 F1 점수를 올린다.
  - pycaret에서 catboost는 gpu 가속이 잘 안되는 듯. ⇒ early_stop을 사용하지 않아서 오래걸림.
  - 훈련, 테스트(검증) 데이터 분리하는 비율은 기본이 효과적. 
  - 훈련, 테스트(검증) 데이터 분리하는 random_state 값을 여러가지로 설정해, 예측 후 결과를 종합하는 것이 효과적.

### 01\. 데이터 수집 [[폴더]](https://github.com/kbjung/Dacon/tree/main/TP2(%EC%9E%A1%EC%BC%80%EC%96%B4)/01_%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%88%98%EC%A7%91)
+ 기존 데이터 + 속성D코드, 속성H코드, 속성L코드 추가 [code](https://github.com/kbjung/Dacon/blob/main/TP2(%EC%9E%A1%EC%BC%80%EC%96%B4)/01_%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%88%98%EC%A7%91/01_01_%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%88%98%EC%A7%91_ver0.1.ipynb)

### 02\. 데이터 분석 [[폴더]](https://github.com/kbjung/Dacon/tree/main/TP2(%EC%9E%A1%EC%BC%80%EC%96%B4)/02_%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B6%84%EC%84%9D)
+ 기본 데이터 분석(2021.12.14 ~ 17) [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/02_데이터분석/02-01_분석ver0.1.html)
  - 속성별 target값 분포 확인
  - 사용자가 이용한 컨텐츠 수 파악한 뒤, 이용 컨텐츠 수별 target 값 비율 확인.(열람한 컨텐츠가 많을 수록 이용을 많이 할 것으로 가정)
  - target 값별로 데이터 셋을 만든 뒤, 각 셋에서 특성마다 유니크 값 개수의 분포를 비교.(특성1의 유니크 값 분포를 target 값이 0, 1일때 비교) 많은 차이가 나는 특성이 훈련/예측에 좋을 것이라 판단.
+ 매칭별 경우의 수로 분석(2021.12.21~25)
  - ver0.2 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/02_데이터분석/02-01_분석ver0.2.html)
  - ver0.3 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/02_데이터분석/02-01_분석ver0.3.html)
  - 매칭별로 나누어, target 값의 분포 확인.
+ target값 별 특성의 분포 확인(2021.12.29~30)
  - ver0.4 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/02_데이터분석/02-01_분석ver0.4.html)
  - 매칭 특성은 사람 선호 특성과 컨텐츠 속성이 같은지 다른지를 알려주기에, 비교되는 두 특성이 있다면 의미 없는 특성이라 판단.
  - ↳ 예상과 반대로 실제 성적이 낮아짐. 매칭 특성과 두 특성 모두 필요한 특성.
  - 최대한 사용되는 특성을 줄이는 방향으로 진행.
+ target값 별 특성의 고유값 분포 시각화(2021.12.31~2022.01.21)
  - ver0.5 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/02_데이터분석/02-01_분석ver0.5.html)
  - 특성 분포 비율, 특성 분포 히스토그램
  - ↳ target값 별 특성 분포가 비슷한 특성 2가지, 애매한 특성 2가지 선별.

### 03\. 모델 선정 및 개선 [[폴더]](https://github.com/kbjung/Dacon/tree/main/TP2(%EC%9E%A1%EC%BC%80%EC%96%B4)/03_%EB%AA%A8%EB%8D%B8%EC%84%A0%EC%A0%95%EB%B0%8F%EA%B0%9C%EC%84%A0)
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
  - ver2.6 : pycaret(이하 py), blend(cat, tuned_lgbm) / combine(이하 comb), numeric(이하 nu) / probabiltily_threshold [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver2.6.html)
+ 속성데이터 추가(이하 data2), 5특성 제거, pb_thr 제한(2021.12.29)
  - ver2.7 : py:cat / comb,nu / pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver2.7.html)
+ data2, 11특성 제거, pb_thr(2021.12.29)
  - ver2.8 : py:cat / comb,nu / pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver2.8.html)
+ data2, 16특성 제거, pb_thr(2021.12.29)
  - ver2.9 : py:cat / comb,nu / pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver2.9.html)
+ data2, 16특성 제거, pb_thr(2021.12.30)
  - 제거 특성(16개) : 기본 5개 + 매칭 특성 6개 + 타겟별 차이 적은 특성 5개
  - ver3.0 : py:cat / nu / pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver3.0.html)
+ data2, 16특성 제거, pb_thr(2021.12.30)
  - 제거 특성(16개) : 기본 5개 + 매칭 특성 6개 + 타겟별 차이 적은 특성 5개
  - ver3.1 : py:cat / nu, bin / pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver3.1.html)
+ data2, 16특성 제거, pb_thr(2021.12.30)
  - 제거 특성(16개) : 기본 5개 + 매칭 특성과 연관없는 특성 11개
  - ver3.2 : py:cat/nu/pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver3.2.html)
+ data2, 27특성 제거, pb_thr(2021.12.31)
  - 제거 특성(27개) : 기본 5개 + 매칭 특성과 연관없는 특성 20개 + 타겟별 차이 적은 특성 2개
  - ver3.3 : py:cat/comb,nu/pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver3.3.html)
+ data2, 29특성 제거, pb_thr(2021.12.31)
  - 제거 특성(29개) : 기본 5개 + 매칭 특성과 연관없는 특성 20개 + 타겟별 차이 적은 특성 4개
  - ver3.4 : py:cat/comb,nu/pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver3.4.html)
+ data2, 5특성 제거, pb_thr(2021.12.31)
  - ver3.5 : py:cat/comb,nu/pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver3.5.html)
+ data2, 5특성 제거, 수치형 특성 지정(16개), pb_thr(2021.01.01)
  - ver3.6 : py:cat/comb,nu(16개)/pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver3.6.html)
+ data2, 6특성 제거, 매칭별 진행(16개), pb_thr(2021.01.01)
  - ver3.7 : py:cat/comb,nu/pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver3.7.html)
+ data2, 6특성 제거, 특정 특성 고유 값 별 진행(2개), pb_thr(2021.01.01)
  - ver3.8 : py:cat/comb,nu/pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver3.8.html)
+ data2, 6특성 제거, pb_thr(2021.01.04)
  - ver3.9 : py:blend(cat,tuned_lgbm)/comb,nu/pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver3.9.html)
+ data2, 4특성 제거, PCA, pb_thr(2021.01.06)
  - ver4.0 : py:blend(cat,tuned_lgbm)/comb,nu,pca(25)/pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver4.0.html)
---
+ 설명
  - cat : catboost
  - data2 : train, test 데이터에 속성 D, H, L 데이터 매칭한 데이터.
  - ohe : one_hot_max_size
  - early : early_stopping_rounds
  - pb_thr : probability_threshold
  - rd : 적용 random_state의 개수
  - test : train_test_split에서 test_size 설정 값
  - ver-.- : 제출한 파일
  - ver-.-.- : 제출 안한 파일, 분석과정 파일 or ver-.-에서 살짝 변경해 테스트한 파일
+ cat/data2, 4특성제거/ohe=2이하,early=50/pb_thr(2021.01.07) ver4.1 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver4.1.html)
+ cat/data2, 4특성제거/ohe=2이하,early=50/pb_thr(2021.01.11) ver4.2 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver4.2.html)
+ cat/data2, 7특성제거/ohe=2이하,early=50/pb_thr(2021.01.12) ver4.3 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver4.3.html)
+ cat/data2, 9특성제거/ohe=2이하,early=50/pb_thr(2021.01.12) ver4.4 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver4.4.html)
+ cat/data2, 9특성제거, rd:5/ohe=2이하,early=50/pb_thr(2021.01.12) ver4.5 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver4.5.html)
+ ✨cat/data2, 7특성제거, rd:5/ohe=2이하,early=50/pb_thr(2021.01.13) ver4.6 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver4.6.html)
+ cat/data2, 4특성제거, rd:5/ohe=2이하,early=50/pb_thr(2021.01.13) ver4.6.1 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver4.6.1.html)
+ cat/data2, 6특성제거, rd:5/ohe=2이하,early=50/pb_thr(2021.01.13) ver4.6.2 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver4.6.2.html)
+ cat/data2, 8특성제거, rd:5/ohe=2이하,early=50/pb_thr(2021.01.13) ver4.7 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver4.7.html)
+ cat/data2, 5특성제거, rd:5/ohe=2이하,early=50/pb_thr(2021.01.14) ver4.8 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver4.8.html)
+ cat/data2, 7특성제거, rd:10/ohe=2이하,early=50/pb_thr(2021.01.14) ver4.9 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver4.9.html)
+ cat/data2, 7특성제거, rd:10/ohe=2이하,early=100/pb_thr(2021.01.18) ver5.0 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver5.0.html)
+ cat/data2, 7특성제거, rd:5/ohe=2이하,early=100/pb_thr(2021.01.18) ver5.1 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver5.1.html)
+ cat/data1, 7특성제거, rd:5/ohe=2이하,early=50/pb_thr(2021.01.18) ver5.2 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver5.2.html)
+ py:blend(cat,tuned_lgbm)/data1, 8특성 제거/comb, nu/pb_thr(2021.01.19) ver5.3 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-02_pycaret_ver5.3.html)
+ cat/data2, 7특성제거, rd:5(sort)/ohe=2이하,early=50/pb_thr(2021.01.19) ver5.4 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver5.4.html)
+ cat/data2, 7특성제거, rd:10(sort)/ohe=2이하,early=50/pb_thr(2021.01.19) ver5.5 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver5.5.html)
+ test_size/cat/data2, 7특성제거, rd:5/ohe=2이하,early=77/pb_thr(2021.01.20) ver5.6.1 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver5.6.1.html)
+ cat/data2, 7특성제거, rd:5/ohe=2이하,early=77, test=0.1/pb_thr(2021.01.20) ver5.6 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver5.6.html)
  - 자체 점수 ↑, 제출 점수 ↓ ⇒ 과대적합
+ cat/data2, 7특성제거, rd:5/ohe=2이하,early=77, test=0.2/pb_thr(2021.01.20) ver5.7 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver5.7.html)
  - 자체 점수 ↑, 제출 점수 ↓ ⇒ 과대적합 ⇒ 기본 세팅으로 적용
+ 특성중요도/cat/data2, 7특성제거, rd:5/ohe=2이하,early=50/pb_thr(2021.01.20) ver5.8.1 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver5.8.1.html)
+ 특성중요도/cat/data2, 4특성제거, rd:5/ohe=2이하,early=50/pb_thr(2021.01.24) ver5.8.2 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver5.8.2.html)
+ cat/data2, 9특성제거, rd:5/ohe=2이하,early=77/pb_thr(2021.01.20) ver5.8 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver5.8.html)
+ cat/data2, 11특성제거, rd:5/ohe=2이하,early=50/pb_thr(2021.01.21) ver5.9 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver5.9.html)
+ cat/data2, 11특성제거, rd:5/ohe=2이하,early=150/pb_thr(2021.01.21) ver6.0 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver6.0.html)
+ cat/data2, 12특성제거, rd:5/ohe=2이하,early=50/pb_thr(2021.01.22) ver6.1 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver6.1.html)
+ cat/data2, 12특성제거, minmax, rd:5/ohe=2이하,early=50/pb_thr(2021.01.22) ver6.2 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver6.2.html)
+ cat/data2, 16특성제거, rd:5/ohe=2이하,early=50/pb_thr(2021.01.22) ver6.3 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver6.3.html)
+ cat/data2, 12특성(50특성제거), rd:5/ohe=2이하,early=50/pb_thr(2021.01.24) ver6.4 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver6.4.html)
+ cat/data2, 15특성제거, rd:5/ohe=2이하,early=50/pb_thr(2021.01.24) ver6.5 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver6.5.html)
+ cat/data2, 7특성제거, rd:5/ohe=5이하,early=50/pb_thr(2021.01.25) ver6.6 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver6.6.html)
+ cat/data2, 7특성제거, rd:5, 매칭:8/ohe=2이하,early=50/pb_thr(2021.01.25) ver6.7 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver6.7.html)
+ cat/data2, 7특성제거, rd:5, 매칭:4/ohe=2이하,early=50/pb_thr(2021.01.28) ver6.8 [code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/03_모델선정및개선/03-04_catboost_ver6.8.html)
### 04\. 결과 종합 [[폴더]](https://github.com/kbjung/Dacon/tree/main/TP2(%EC%9E%A1%EC%BC%80%EC%96%B4)/04_%EA%B2%B0%EA%B3%BC_%ED%95%A9%EC%82%B0)
+ top3 결과 종합 ver0.1(2022.01.28)[code(html)](https://kbjung.github.io/Dacon/TP2(잡케어)/04_결과_합산/04-01_results_ver0.1.html)
