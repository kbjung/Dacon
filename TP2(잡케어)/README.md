# ๐ค๐ผ ํํ๋ก์ ํธ2 [[์์ธ๋ด์ฉ]](https://github.com/kbjung/Dacon/tree/main/TP2(์ก์ผ์ด))

## ๐ ๋ํ ์ ๋ณด
+ ๋ํ : ์ก์ผ์ด ์ถ์ฒ ์๊ณ ๋ฆฌ์ฆ ๊ฒฝ์ง๋ํ [[๋ํ ๋งํฌ]](https://dacon.io/competitions/official/235863/overview/description)
+ ๊ธฐ๊ฐ : 2021.12.06 19:00 ~ 2022.01.28
+ ์ฃผ์  : ๊ตฌ์ง์์ ์ด๋ ฅ์๋ฅผ ์ธ๊ณต์ง๋ฅ ๊ธฐ์ ๋ก ์ง๋ฌด์ญ๋์ ์๋ ๋ถ์ํ์ฌ ๊ฐ์ธ๋ณ ๋ง์ถคํ ์ปจํ์ธ  ์ถ์ฒ ๋ชจ๋ธ ๊ตฌ์ถ
+ **๋ชฉํ : ๋ฐ์ดํฐ ์ ์ฒ๋ฆฌ&๋ถ์, ๋จธ์ ๋ฌ๋ ํ์ฉ ๊ธฐ์  ํฅ์**


## ๐จโ๐ป ํ ์ ๋ณด
+ ํ๋ช : ๋ณด๋ ์ฝ๋ฆฌ
+ ํ์ฅ : **๊น๋ฒ์ค** ๐ข
+ ํ์ : ์ต๋ํธ, ๊น์ง์ฐ

## ๐ง ํ์ฉ ๊ธฐ์ (Python)
  - ๋ฐ์ดํฐ ์์ง : pandas
  - ๋ฐ์ดํฐ ํ์ : matplotlib, numpy
  - ๋จธ์  ๋ฌ๋ ๋ชจ๋ธ ๋ฐ ๋ผ์ด๋ธ๋ฌ๋ฆฌ : pycaret(classification), randomforest, catboost, naive bayes
  - ํ๊ฐ์งํ : F1-score(๋ํํ๊ฐ์งํ)
  
## ๐ ์ฑ๊ณผ
+ ๋ด์ฉ ์ ๋ฆฌ : [[notion]](https://www.notion.so/Dacon-2d14915013594e6cb30ad36c34ff4c64)
+ ์ ์ ๊ธฐ๋ก : [[์คํ๋ ๋์ํธ]](https://docs.google.com/spreadsheets/d/18vwewjISwsBQNSL2arV_i5q9LlNfJ-QEtrCiNTuGIJ4/edit?usp=sharing)
  - โจ public ์ต๊ณ ์  : **37๋ฑ**(์ด 1,335๋ช ์ฐธ๊ฐ) ๊ธฐ๋ก(**0.701834167 ์ **, 2022-01-13 11:08:38)
  - โจ private ์ต๊ณ ์  : **189๋ฑ**(์ด 1,335๋ช ์ฐธ๊ฐ) ๊ธฐ๋ก(**0.6997627581 ์ **)
+ ๋ฐฐ์ด ์   
  - ์ ์ ํ ํน์ฑ ์ ํ ํ์. ๋ง์ ํน์ฑ์ ๋ธ์ด์ฆ ๋ฐ์์ํด.
  - ๊ธฐ์ค ํ๋ฅ  ์กฐ์ (probability threshold)์ด ํจ๊ณผ๊ฐ ๋์.
  - ๋ฐ์ด์์ ๋๋์ด ์งํํ๋ ๊ฒ์ด F1 ์ ์๋ฅผ ์ฌ๋ฆฐ๋ค.
  - pycaret์์ catboost๋ gpu ๊ฐ์์ด ์ ์๋๋ ๋ฏ. โ early_stop์ ์ฌ์ฉํ์ง ์์์ ์ค๋๊ฑธ๋ฆผ.
  - ํ๋ จ, ํ์คํธ(๊ฒ์ฆ) ๋ฐ์ดํฐ ๋ถ๋ฆฌํ๋ ๋น์จ์ ๊ธฐ๋ณธ์ด ํจ๊ณผ์ . 
  - ํ๋ จ, ํ์คํธ(๊ฒ์ฆ) ๋ฐ์ดํฐ ๋ถ๋ฆฌํ๋ random_state ๊ฐ์ ์ฌ๋ฌ๊ฐ์ง๋ก ์ค์ ํด, ์์ธก ํ ๊ฒฐ๊ณผ๋ฅผ ์ขํฉํ๋ ๊ฒ์ด ํจ๊ณผ์ .

## 01\. ๋ฐ์ดํฐ ์์ง [[ํด๋]](https://github.com/kbjung/Dacon/tree/main/TP2(%EC%9E%A1%EC%BC%80%EC%96%B4)/01_%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%88%98%EC%A7%91)
+ ๊ธฐ์กด ๋ฐ์ดํฐ + ์์ฑD์ฝ๋, ์์ฑH์ฝ๋, ์์ฑL์ฝ๋ ์ถ๊ฐ [code](https://github.com/kbjung/Dacon/blob/main/TP2(%EC%9E%A1%EC%BC%80%EC%96%B4)/01_%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%88%98%EC%A7%91/01_01_%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%88%98%EC%A7%91_ver0.1.ipynb)

## 02\. ๋ฐ์ดํฐ ๋ถ์ [[ํด๋]](https://github.com/kbjung/Dacon/tree/main/TP2(%EC%9E%A1%EC%BC%80%EC%96%B4)/02_%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B6%84%EC%84%9D)
+ ๊ธฐ๋ณธ ๋ฐ์ดํฐ ๋ถ์(2021.12.14 ~ 17) [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/02_๋ฐ์ดํฐ๋ถ์/02-01_๋ถ์ver0.1.html)
  - ์์ฑ๋ณ target๊ฐ ๋ถํฌ ํ์ธ
  - ์ฌ์ฉ์๊ฐ ์ด์ฉํ ์ปจํ์ธ  ์ ํ์ํ ๋ค, ์ด์ฉ ์ปจํ์ธ  ์๋ณ target ๊ฐ ๋น์จ ํ์ธ.(์ด๋ํ ์ปจํ์ธ ๊ฐ ๋ง์ ์๋ก ์ด์ฉ์ ๋ง์ด ํ  ๊ฒ์ผ๋ก ๊ฐ์ )
  - target ๊ฐ๋ณ๋ก ๋ฐ์ดํฐ ์์ ๋ง๋  ๋ค, ๊ฐ ์์์ ํน์ฑ๋ง๋ค ์ ๋ํฌ ๊ฐ ๊ฐ์์ ๋ถํฌ๋ฅผ ๋น๊ต.(ํน์ฑ1์ ์ ๋ํฌ ๊ฐ ๋ถํฌ๋ฅผ target ๊ฐ์ด 0, 1์ผ๋ ๋น๊ต) ๋ง์ ์ฐจ์ด๊ฐ ๋๋ ํน์ฑ์ด ํ๋ จ/์์ธก์ ์ข์ ๊ฒ์ด๋ผ ํ๋จ.
+ ๋งค์นญ๋ณ ๊ฒฝ์ฐ์ ์๋ก ๋ถ์(2021.12.21~25)
  - ver0.2 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/02_๋ฐ์ดํฐ๋ถ์/02-01_๋ถ์ver0.2.html)
  - ver0.3 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/02_๋ฐ์ดํฐ๋ถ์/02-01_๋ถ์ver0.3.html)
  - ๋งค์นญ๋ณ๋ก ๋๋์ด, target ๊ฐ์ ๋ถํฌ ํ์ธ.
+ target๊ฐ ๋ณ ํน์ฑ์ ๋ถํฌ ํ์ธ(2021.12.29~30)
  - ver0.4 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/02_๋ฐ์ดํฐ๋ถ์/02-01_๋ถ์ver0.4.html)
  - ๋งค์นญ ํน์ฑ์ ์ฌ๋ ์ ํธ ํน์ฑ๊ณผ ์ปจํ์ธ  ์์ฑ์ด ๊ฐ์์ง ๋ค๋ฅธ์ง๋ฅผ ์๋ ค์ฃผ๊ธฐ์, ๋น๊ต๋๋ ๋ ํน์ฑ์ด ์๋ค๋ฉด ์๋ฏธ ์๋ ํน์ฑ์ด๋ผ ํ๋จ.
  - โณ ์์๊ณผ ๋ฐ๋๋ก ์ค์  ์ฑ์ ์ด ๋ฎ์์ง. ๋งค์นญ ํน์ฑ๊ณผ ๋ ํน์ฑ ๋ชจ๋ ํ์ํ ํน์ฑ.
  - ์ต๋ํ ์ฌ์ฉ๋๋ ํน์ฑ์ ์ค์ด๋ ๋ฐฉํฅ์ผ๋ก ์งํ.
+ target๊ฐ ๋ณ ํน์ฑ์ ๊ณ ์ ๊ฐ ๋ถํฌ ์๊ฐํ(2021.12.31~2022.01.21)
  - ver0.5 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/02_๋ฐ์ดํฐ๋ถ์/02-01_๋ถ์ver0.5.html)
  - ํน์ฑ ๋ถํฌ ๋น์จ, ํน์ฑ ๋ถํฌ ํ์คํ ๊ทธ๋จ
  - โณ target๊ฐ ๋ณ ํน์ฑ ๋ถํฌ๊ฐ ๋น์ทํ ํน์ฑ 2๊ฐ์ง, ์ ๋งคํ ํน์ฑ 2๊ฐ์ง ์ ๋ณ.

## 03\. ๋ชจ๋ธ ์ ์  ๋ฐ ๊ฐ์  [[ํด๋]](https://github.com/kbjung/Dacon/tree/main/TP2(%EC%9E%A1%EC%BC%80%EC%96%B4)/03_%EB%AA%A8%EB%8D%B8%EC%84%A0%EC%A0%95%EB%B0%8F%EA%B0%9C%EC%84%A0)
+ ๊ธฐ๋ณธ ํ์คํธ (2021.12.14) [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver0.1.html)
  - ver0.1 : pycaret, cat / combine
  - ver0.1.1 : ๋ชจ๋ธ ๋น๊ต [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver0.1.1.html)
+ 10๊ฐ ์ด์ ์ปจํ์ธ  ์ฌ์ฉ์ ๋ฐ์ดํฐ๋ก ์์ธก(2021.12.14) [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver0.2.html)
  - ver0.2 : pycaret, rf / combine
+ 5๊ฐ ์ด์ ์ปจํ์ธ  ์ฌ์ฉ์ ๋ฐ์ดํฐ๋ก ์์ธก(2021.12.15)
  - ver0.3 : pycaret, nb / combine [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver0.3.html)
  - ver0.4 : pycaret, nb / combine, cardinality [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver0.4.html)
  - ver0.5 : pycaret, cat / combine [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver0.5.html)
+ ํน์  ํน์ฑ ์ ๊ฑฐ(2021.12.17)
  - 1๊ฐ์ผ๋ก ์ฑ์์ง person_prefer_f, g ํน์ฑ ์ ๊ฑฐ
  - ver0.6 : pycaret, cat, tune [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver0.6.html)
  - ver0.7 : pycaret, cat, tune / combine [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver0.7.html)
  - target๊ฐ ๊ธฐ์ค, ํน์ฑ๋ณ ์ ๋ํฌ ๊ฐ์ด ๋น๊ต์  ๋ง์ด ๋ค๋ฅธ ํน์ฑ๋ง ์ ํ(22๊ฐ)
  - ver0.8 : pycaret, cat / combine [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver0.8.html)
+ 1๊ฐ์ผ๋ก ์ฑ์์ง person_prefer_f, g ํน์ฑ ์ ๊ฑฐ, ์์ํ ํน์ฑ ์์นํ ์ง์ (2021.12.18)
  - ver0.9 : pycaret, cat / combine, numeric [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver0.9.html)
+ ๊ธฐ๋ณธ2, f, g, ์ฌ์ฉ์ ๋ฒํธ, ์ปจํ์ธ  ๋ฒํธ ์ด 6๊ฐ ํน์ฑ ์ ๊ฑฐ(2021.12.19)
  - ver1.0 : pycaret, nb / combine [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver1.0.html)
  - ver1.1 : pycaret, tuned_nb / combine [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver1.1.html)
  - ์ถ๊ฐ)์์ํ ํน์ฑ ์์นํ ์ง์ 
  - ver1.2 : pycaret, nb / combine [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver1.2.html)
+ target๊ฐ ๊ธฐ์ค, ํน์ฑ๋ณ ์ ๋ํฌ ๊ฐ์ด ๋น๊ต์  ๋ง์ด ๋ค๋ฅธ ํน์ฑ๋ง ์ ํ(22ํน์ฑ)(2021.12.20)
  - ver1.3 : pycaret, nb / combine, ์์ํ -> ์์นํ [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver1.3.html)
+ target๊ฐ ๊ธฐ์ค, ํน์ฑ๋ณ ์ ๋ํฌ ๊ฐ์ด ๋น๊ต์  ๋ง์ด ๋ค๋ฅธ ํน์ฑ๋ง ์ ํ(25ํน์ฑ)(2021.12.20)
  - ver1.4 : pycaret, nb / combine, ์์ํ->์์นํ [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver1.4.html)
  - ver1.5 : pycaret, cat / combine, ์์ํ->์์นํ [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver1.5.html)
+ ๊ธฐ๋ณธ2ํน์ฑ ์ ๊ฑฐ(2021.12.21)
  - ver1.6 : pycaret, cat / combine, ์์ํ->์์นํ [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver1.6.html)
+ 25ํน์ฑ, 8๋งค์นญ๋ณ ํ๋ จ(2021.12.21)
  - ver1.7 : pycaret, nb / combine, ์์ํ->์์นํ [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver1.7.html)
+ 25ํน์ฑ, 8๋งค์นญ๋ณ ํ๋ จ, blend(2021.12.22)
  - ver1.8 : pycaret, nb/cat / combine, ์์นํ [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver1.8.html)
+ 25ํน์ฑ, 8๋งค์นญ๋ณ ํ๋ จ, ๋จ๊ณ๋ณ blend(2021.12.22)
  - ver1.9 : pycaret, blend 2 models(nb, cat, gbc, lr ์ค) / combine, ์์นํ [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver1.9.html)
  - ver2.0 : pycaret, blend 2 models(nb, cat, gbc ์ค) / combine, ์์นํ, minmax [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver2.0.html)
+ 25ํน์ฑ, 8๋งค์นญ๋ณ ํ๋ จ, blend(2021.12.22)
  - ver2.1 : pycaret, blend 3 models(nb, cat, gbc) / combine, ์์นํ, minmax [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver2.1.html)
+ 25ํน์ฑ, 4๋งค์นญ๋ณ ํ๋ จ, ๋จ๊ณ๋ณ blend(2021.12.25)
  - ver.2.2 : pycaret, blend 2 models(nb, cat, gbc ์ค) / combine, ์์นํ, minmax [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver2.2.html)
+ 5ํน์ฑ ์ ๊ฑฐ, probability_threshold ์ ํ(2021.12.27)
  - ver2.3 : pycaret, cat / combine, ์์นํ / probability_threshold [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver2.3.html)
  - ver2.4 : pycaret, cat / combine, ์์นํ / probability_threshold [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver2.4.html)
+ 26ํน์ฑ, probability_threshold ์ ํ(2021.12.27)
  - ver2.5 : pycaret, cat / combine, ์์นํ / probability_threshold [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver2.5.html)
+ 26ํน์ฑ, blend, probability_threshold(์ดํ pb_thr) ์ ํ(2021.12.28)
  - ver2.6 : pycaret(์ดํ py), blend(cat, tuned_lgbm) / combine(์ดํ comb), numeric(์ดํ nu) / probabiltily_threshold [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver2.6.html)
+ ์์ฑ๋ฐ์ดํฐ ์ถ๊ฐ(์ดํ data2), 5ํน์ฑ ์ ๊ฑฐ, pb_thr ์ ํ(2021.12.29)
  - ver2.7 : py:cat / comb,nu / pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver2.7.html)
+ data2, 11ํน์ฑ ์ ๊ฑฐ, pb_thr(2021.12.29)
  - ver2.8 : py:cat / comb,nu / pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver2.8.html)
+ data2, 16ํน์ฑ ์ ๊ฑฐ, pb_thr(2021.12.29)
  - ver2.9 : py:cat / comb,nu / pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver2.9.html)
+ data2, 16ํน์ฑ ์ ๊ฑฐ, pb_thr(2021.12.30)
  - ์ ๊ฑฐ ํน์ฑ(16๊ฐ) : ๊ธฐ๋ณธ 5๊ฐ + ๋งค์นญ ํน์ฑ 6๊ฐ + ํ๊ฒ๋ณ ์ฐจ์ด ์ ์ ํน์ฑ 5๊ฐ
  - ver3.0 : py:cat / nu / pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver3.0.html)
+ data2, 16ํน์ฑ ์ ๊ฑฐ, pb_thr(2021.12.30)
  - ์ ๊ฑฐ ํน์ฑ(16๊ฐ) : ๊ธฐ๋ณธ 5๊ฐ + ๋งค์นญ ํน์ฑ 6๊ฐ + ํ๊ฒ๋ณ ์ฐจ์ด ์ ์ ํน์ฑ 5๊ฐ
  - ver3.1 : py:cat / nu, bin / pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver3.1.html)
+ data2, 16ํน์ฑ ์ ๊ฑฐ, pb_thr(2021.12.30)
  - ์ ๊ฑฐ ํน์ฑ(16๊ฐ) : ๊ธฐ๋ณธ 5๊ฐ + ๋งค์นญ ํน์ฑ๊ณผ ์ฐ๊ด์๋ ํน์ฑ 11๊ฐ
  - ver3.2 : py:cat/nu/pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver3.2.html)
+ data2, 27ํน์ฑ ์ ๊ฑฐ, pb_thr(2021.12.31)
  - ์ ๊ฑฐ ํน์ฑ(27๊ฐ) : ๊ธฐ๋ณธ 5๊ฐ + ๋งค์นญ ํน์ฑ๊ณผ ์ฐ๊ด์๋ ํน์ฑ 20๊ฐ + ํ๊ฒ๋ณ ์ฐจ์ด ์ ์ ํน์ฑ 2๊ฐ
  - ver3.3 : py:cat/comb,nu/pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver3.3.html)
+ data2, 29ํน์ฑ ์ ๊ฑฐ, pb_thr(2021.12.31)
  - ์ ๊ฑฐ ํน์ฑ(29๊ฐ) : ๊ธฐ๋ณธ 5๊ฐ + ๋งค์นญ ํน์ฑ๊ณผ ์ฐ๊ด์๋ ํน์ฑ 20๊ฐ + ํ๊ฒ๋ณ ์ฐจ์ด ์ ์ ํน์ฑ 4๊ฐ
  - ver3.4 : py:cat/comb,nu/pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver3.4.html)
+ data2, 5ํน์ฑ ์ ๊ฑฐ, pb_thr(2021.12.31)
  - ver3.5 : py:cat/comb,nu/pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver3.5.html)
+ data2, 5ํน์ฑ ์ ๊ฑฐ, ์์นํ ํน์ฑ ์ง์ (16๊ฐ), pb_thr(2021.01.01)
  - ver3.6 : py:cat/comb,nu(16๊ฐ)/pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver3.6.html)
+ data2, 6ํน์ฑ ์ ๊ฑฐ, ๋งค์นญ๋ณ ์งํ(16๊ฐ), pb_thr(2021.01.01)
  - ver3.7 : py:cat/comb,nu/pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver3.7.html)
+ data2, 6ํน์ฑ ์ ๊ฑฐ, ํน์  ํน์ฑ ๊ณ ์  ๊ฐ ๋ณ ์งํ(2๊ฐ), pb_thr(2021.01.01)
  - ver3.8 : py:cat/comb,nu/pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver3.8.html)
+ data2, 6ํน์ฑ ์ ๊ฑฐ, pb_thr(2021.01.04)
  - ver3.9 : py:blend(cat,tuned_lgbm)/comb,nu/pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver3.9.html)
+ data2, 4ํน์ฑ ์ ๊ฑฐ, PCA, pb_thr(2021.01.06)
  - ver4.0 : py:blend(cat,tuned_lgbm)/comb,nu,pca(25)/pb_thr [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver4.0.html)
---
+ ์ค๋ช
  - cat : catboost
  - data2 : train, test ๋ฐ์ดํฐ์ ์์ฑ D, H, L ๋ฐ์ดํฐ ๋งค์นญํ ๋ฐ์ดํฐ.
  - ohe : one_hot_max_size
  - early : early_stopping_rounds
  - pb_thr : probability_threshold
  - rd : ์ ์ฉ random_state์ ๊ฐ์
  - test : train_test_split์์ test_size ์ค์  ๊ฐ
  - ver-.- : ์ ์ถํ ํ์ผ
  - ver-.-.- : ์ ์ถ ์ํ ํ์ผ, ๋ถ์๊ณผ์  ํ์ผ or ver-.-์์ ์ด์ง ๋ณ๊ฒฝํด ํ์คํธํ ํ์ผ
+ cat/data2, 4ํน์ฑ์ ๊ฑฐ/ohe=2์ดํ,early=50/pb_thr(2021.01.07) ver4.1 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver4.1.html)
+ cat/data2, 4ํน์ฑ์ ๊ฑฐ/ohe=2์ดํ,early=50/pb_thr(2021.01.11) ver4.2 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver4.2.html)
+ cat/data2, 7ํน์ฑ์ ๊ฑฐ/ohe=2์ดํ,early=50/pb_thr(2021.01.12) ver4.3 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver4.3.html)
+ cat/data2, 9ํน์ฑ์ ๊ฑฐ/ohe=2์ดํ,early=50/pb_thr(2021.01.12) ver4.4 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver4.4.html)
+ cat/data2, 9ํน์ฑ์ ๊ฑฐ, rd:5/ohe=2์ดํ,early=50/pb_thr(2021.01.12) ver4.5 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver4.5.html)
+ โจcat/data2, 7ํน์ฑ์ ๊ฑฐ, rd:5/ohe=2์ดํ,early=50/pb_thr(2021.01.13) ver4.6 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver4.6.html)
+ cat/data2, 4ํน์ฑ์ ๊ฑฐ, rd:5/ohe=2์ดํ,early=50/pb_thr(2021.01.13) ver4.6.1 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver4.6.1.html)
+ cat/data2, 6ํน์ฑ์ ๊ฑฐ, rd:5/ohe=2์ดํ,early=50/pb_thr(2021.01.13) ver4.6.2 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver4.6.2.html)
+ cat/data2, 8ํน์ฑ์ ๊ฑฐ, rd:5/ohe=2์ดํ,early=50/pb_thr(2021.01.13) ver4.7 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver4.7.html)
+ cat/data2, 5ํน์ฑ์ ๊ฑฐ, rd:5/ohe=2์ดํ,early=50/pb_thr(2021.01.14) ver4.8 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver4.8.html)
+ cat/data2, 7ํน์ฑ์ ๊ฑฐ, rd:10/ohe=2์ดํ,early=50/pb_thr(2021.01.14) ver4.9 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver4.9.html)
+ cat/data2, 7ํน์ฑ์ ๊ฑฐ, rd:10/ohe=2์ดํ,early=100/pb_thr(2021.01.18) ver5.0 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver5.0.html)
+ cat/data2, 7ํน์ฑ์ ๊ฑฐ, rd:5/ohe=2์ดํ,early=100/pb_thr(2021.01.18) ver5.1 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver5.1.html)
+ cat/data1, 7ํน์ฑ์ ๊ฑฐ, rd:5/ohe=2์ดํ,early=50/pb_thr(2021.01.18) ver5.2 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver5.2.html)
+ py:blend(cat,tuned_lgbm)/data1, 8ํน์ฑ ์ ๊ฑฐ/comb, nu/pb_thr(2021.01.19) ver5.3 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-02_pycaret_ver5.3.html)
+ cat/data2, 7ํน์ฑ์ ๊ฑฐ, rd:5(sort)/ohe=2์ดํ,early=50/pb_thr(2021.01.19) ver5.4 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver5.4.html)
+ cat/data2, 7ํน์ฑ์ ๊ฑฐ, rd:10(sort)/ohe=2์ดํ,early=50/pb_thr(2021.01.19) ver5.5 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver5.5.html)
+ test_size/cat/data2, 7ํน์ฑ์ ๊ฑฐ, rd:5/ohe=2์ดํ,early=77/pb_thr(2021.01.20) ver5.6.1 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver5.6.1.html)
+ cat/data2, 7ํน์ฑ์ ๊ฑฐ, rd:5/ohe=2์ดํ,early=77, test=0.1/pb_thr(2021.01.20) ver5.6 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver5.6.html)
  - ์์ฒด ์ ์ โ, ์ ์ถ ์ ์ โ โ ๊ณผ๋์ ํฉ
+ cat/data2, 7ํน์ฑ์ ๊ฑฐ, rd:5/ohe=2์ดํ,early=77, test=0.2/pb_thr(2021.01.20) ver5.7 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver5.7.html)
  - ์์ฒด ์ ์ โ, ์ ์ถ ์ ์ โ โ ๊ณผ๋์ ํฉ โ ๊ธฐ๋ณธ ์ธํ์ผ๋ก ์ ์ฉ
+ ํน์ฑ์ค์๋/cat/data2, 7ํน์ฑ์ ๊ฑฐ, rd:5/ohe=2์ดํ,early=50/pb_thr(2021.01.20) ver5.8.1 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver5.8.1.html)
+ ํน์ฑ์ค์๋/cat/data2, 4ํน์ฑ์ ๊ฑฐ, rd:5/ohe=2์ดํ,early=50/pb_thr(2021.01.24) ver5.8.2 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver5.8.2.html)
+ cat/data2, 9ํน์ฑ์ ๊ฑฐ, rd:5/ohe=2์ดํ,early=77/pb_thr(2021.01.20) ver5.8 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver5.8.html)
+ cat/data2, 11ํน์ฑ์ ๊ฑฐ, rd:5/ohe=2์ดํ,early=50/pb_thr(2021.01.21) ver5.9 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver5.9.html)
+ cat/data2, 11ํน์ฑ์ ๊ฑฐ, rd:5/ohe=2์ดํ,early=150/pb_thr(2021.01.21) ver6.0 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver6.0.html)
+ cat/data2, 12ํน์ฑ์ ๊ฑฐ, rd:5/ohe=2์ดํ,early=50/pb_thr(2021.01.22) ver6.1 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver6.1.html)
+ cat/data2, 12ํน์ฑ์ ๊ฑฐ, minmax, rd:5/ohe=2์ดํ,early=50/pb_thr(2021.01.22) ver6.2 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver6.2.html)
+ cat/data2, 16ํน์ฑ์ ๊ฑฐ, rd:5/ohe=2์ดํ,early=50/pb_thr(2021.01.22) ver6.3 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver6.3.html)
+ cat/data2, 12ํน์ฑ(50ํน์ฑ์ ๊ฑฐ), rd:5/ohe=2์ดํ,early=50/pb_thr(2021.01.24) ver6.4 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver6.4.html)
+ cat/data2, 15ํน์ฑ์ ๊ฑฐ, rd:5/ohe=2์ดํ,early=50/pb_thr(2021.01.24) ver6.5 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver6.5.html)
+ cat/data2, 7ํน์ฑ์ ๊ฑฐ, rd:5/ohe=5์ดํ,early=50/pb_thr(2021.01.25) ver6.6 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver6.6.html)
+ cat/data2, 7ํน์ฑ์ ๊ฑฐ, rd:5, ๋งค์นญ:8/ohe=2์ดํ,early=50/pb_thr(2021.01.25) ver6.7 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver6.7.html)
+ cat/data2, 7ํน์ฑ์ ๊ฑฐ, rd:5, ๋งค์นญ:4/ohe=2์ดํ,early=50/pb_thr(2021.01.28) ver6.8 [code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/03_๋ชจ๋ธ์ ์ ๋ฐ๊ฐ์ /03-04_catboost_ver6.8.html)
## 04\. ๊ฒฐ๊ณผ ์ขํฉ [[ํด๋]](https://github.com/kbjung/Dacon/tree/main/TP2(%EC%9E%A1%EC%BC%80%EC%96%B4)/04_%EA%B2%B0%EA%B3%BC_%ED%95%A9%EC%82%B0)
+ top3 ๊ฒฐ๊ณผ ์ขํฉ ver0.1(2022.01.28)[code(html)](https://kbjung.github.io/Dacon/TP2(์ก์ผ์ด)/04_๊ฒฐ๊ณผ_ํฉ์ฐ/04-01_results_ver0.1.html)
