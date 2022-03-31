# Naverstocktextmining
## Toy Project
장중 혹은 장시작전의 종목관련 뉴스는 주가에 영향을 주지 않을까 하는 의문에서 시작된 공부겸 미니프로젝트<br>
Data:네이버 금융의 현대차 종목 2021년 뉴스의 제목 전체 크롤링 2021.5월 23일~ 2021.12.31일<br>
방법론: 해당 뉴스가 나온일의 주가가 상승하면 레이블 1 등하락시 0부여하여 gpt2로 학습 후 테스트 수행<br>


![](https://postfiles.pstatic.net/MjAyMjAxMTRfMTcw/MDAxNjQyMDkyNTU1MjYy.XaPgLBVCEfn1z1X8oiqk2R_8nBqs2JK1QJslj06frygg.D8zCTbhoagUpQh_VaYcdeW8JVcKjGzUhqmxrN9cCpDYg.PNG.ps712/image.png?type=w773)
<br>
현대차 관련 뉴스의 월별 분포
<br>
![](https://postfiles.pstatic.net/MjAyMjAxMTRfMTM3/MDAxNjQyMDkyOTk5MDM1.49UuMKAgrYFynjigYeRAjLdQB_msgOxxfRJolOBqu48g.tm5ObnOhyTYakdS10coZM-1tCYaHwZLsCaqOZJc89jgg.PNG.ps712/image.png?type=w773)
<br>
요일별 분포(토,일제외)
<br>
![](https://postfiles.pstatic.net/MjAyMjAxMTRfMjE4/MDAxNjQyMDkzMDM5NjI5.o2Oj8QXsfoLl0d121kepQC8m8yFMCkLnjwYMwjRiMn0g.54UIOwoTHWyNyow_UqKDC5eTQmXYmQNbr6t6DyMHdOgg.PNG.ps712/image.png?type=w773)
<br>
뉴스 해당일에 주가 상승시 레이블 1 변동없거나 하락시 0 부여
<br>
![](https://postfiles.pstatic.net/MjAyMjAxMTRfMTU1/MDAxNjQyMDkzMDg4NTAy.51bc2jalz_tnZEqSPdERykM-T5Hf0gPFD0QmvMxE0CUg.Cd51bxbH_ysa665Ui3bTW9XX7zQon0LX6HanEIMZZAog.PNG.ps712/image.png?type=w773)
<br>
(기사제목이 긍정적이라고해서..반드시 주가상승으로 연결되지는 않는것으로 보임..)
<br>
상승과 등하락 분포
<br>
![](https://postfiles.pstatic.net/MjAyMjAxMTRfMTEz/MDAxNjQyMDkzMTY2ODQ5.NU13zK81cy9Y3ifOAktT_Lr2fF_I_lNTSOmW1UsnuM4g._Qpakphlv4pEVmkErNGlj0LHf9fwVadLwVK4kmzodbcg.PNG.ps712/image.png?type=w773)
<br>
형태소 분리 된 명사 top50
<br>
![](https://postfiles.pstatic.net/MjAyMjAxMTRfMTM2/MDAxNjQyMDkzMjE5MjA5.vlXoERxlgIM4wHkaaj_FCwOjZTzL_mwm2vccCupLopQg.UHOlh0eWTwEukLH-4ka9t08xoc5u3TGKmCB-sKxnoyog.PNG.ps712/image.png?type=w773)
<br>
워드클라우드
<br>
![](https://postfiles.pstatic.net/MjAyMjAxMTRfMjgz/MDAxNjQyMDkzMjY2MDc0.6vfpC68GF8ui5kGc-Jlb6PxAOgSlEE-Dkhwm0huu6Wsg.zTR0KvcveanXH8SSPu4BOBFpINOmnRlw0jBoc62q_T0g.PNG.ps712/image.png?type=w773)
<br>

학습결과 검증용셋의 정확도는 60~70사이<br>
![](https://postfiles.pstatic.net/MjAyMjAxMTRfOTkg/MDAxNjQyMDkzMzYxOTc4.IaUvzxvxJyoILLyYa_fKRoIim3VR7yEWB-z5tquMlB8g.n1CnIY7ZIdnNZXV5PiYi0h099j4fjx_c3DUpwVrD8e4g.PNG.ps712/image.png?type=w773)

테스트셋(전체데이터의 25%)의 정확도는 71퍼센트<br>
![](https://postfiles.pstatic.net/MjAyMjAxMTRfMTY5/MDAxNjQyMDkzMzI5OTA5.jXOK68mUYeKDPOOCCAmuQPMxM3gZ8F8YD-yFv2HXOJ4g.rYudCAYHjUUXAvq7V8slqfsBDeqLFTBSqIjn-2Ys9lwg.PNG.ps712/image.png?type=w773)

<br>
네이버 영화리뷰데이터를 gpt2로 학습했을시 정확도는 87%내외였다<br>
이와비교하면 상당히 낮은 수치이다<br>
현대차 이외 뉴스크롤링 데이터가 많은 삼성전자,네이버,카카오 등도 수행해보았지만 60~70%내외였고<br>
2021년의 테스트셋이 아닌 2022년도 뉴스를 새로모아서 테스트한다면 아마 71%보다는 적을것으로 보인다<br>
이번 미니프로젝트는 마치 영화의 감정분석처럼 해보았다 <br>
실제로는 호재가 공시되거나 뉴스나오면 주가는 급등하기도하고 악재 등으로 인해 급락하기도 하지만 <br>
주가를 바로움직일만한 호재나 악재는 빈번하지 않기 때문에 미치는 영향은 작은 것으로 보인다 <br>
<br>
다음에 주가예측을 할 기회가 된다면..<br>
뉴스제목을 주요변수로 하여 분석하기 보다는 시계열 등 전통적인 분석기법에 보조변수로 활용해보려고 한다<br>

