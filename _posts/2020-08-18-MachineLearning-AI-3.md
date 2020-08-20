---
title: "[KAIST AI 교육 :: 데이터 분석 및 예측] 3"
date: 2020-08-20 21:00:15 -0400
categories: MachineLearning DataAnalyze
---
# 경사하강법(Gradient Descend Algorithm)

<hr/>
<div style = "font-size :0.8em">
  <a href = "https://can019.github.io/machinelearning/dataanalyze/MachineLearning-AI-3/">지난 포스팅</a> 요약 :: 선형회귀법은 Cost가 가장 작은 model을 구하는 것이다. <br/>
  오늘 포스팅 :: 작은 Cost를 구하는 법인 경사하강법(Gradient Descend Algorithm)에 대해 알아보자.
  <div>
    <h3 style = "font-size :1.2em"> 경사하강법</h3><br/>
    <div style = "margin-left : 30px">
       경사하강법은 많은 최소값 탐색 문제에 사용되며 특히 근사값을 구하는 문제에서 많이 사용됩니다.<br/><br/>
       쉽게 설명하기 위해 Cost그래프를 통해 설명하겠습니다.<br/><br/>
       <img src="/assets/photos/20200820_3.png" width="450">
        <span style = "font-size : 0.8em">Cost 그래프 예시</span><br/><br/>
        Cost(w)의 그래프입니다. 여기서 익숙치 않아 간혹 헷갈리는 포인트가 있는데<br/>
        'x축, y축이 뭐지?'입니다.'<br/><br/>
       Cost 그래프의 x축은 w, y축은 Cost입니다.
       Cost 그래프는 w를 준 후 data,label을 곱한 그래프입니다.<br/><br/>
       
       x축은 일단 w를 의미합니다. 여기까진 실수 안하시는데 그 다음 y축이 무엇이냐..에서 실수를 하십니다.<br/><br/>

       w가 1이라고 할 때 H(x) = x, w가 2라면 H(x) = 2x가 됩니다.<br/><br/>
       이 때 data, label set이 [x1,y1],[x2,y2],[x3,y3]라고 할 때<br/><br/>
       w=1일 때 cost는 <img src="https://latex.codecogs.com/png.latex?(x1-y1)^{2}+(x2-y2)^{2}+(x3-y3)^{2}" title="(x1-y1)^{2}+(x2-y2)^{2}+(x3-y3)^{2}}" /><br/><br/>
       w=2일 때 cost는 <img src="https://latex.codecogs.com/png.latex?(2x1-y1)^{2}+(2x2-y2)^{2}+(2x3-y3)^{2}" title="(2x1-y1)^{2}+(2x2-y2)^{2}+(2x3-y3)^{2}}" /><br/><br/>
       가 됩니다.<br/><br/>
       
       이제 

    </div>
  <div>
    <h3 style = "font-size :1.2em"> 제목</h3><br/>
    <div style = "margin-left : 30px">

    </div>
  </div>
 </div>


  <hr/>
  ***미완성인 포스팅입니다***<br/>
   <blockquote> 공부하며 작성하는 포스팅이기 때문에 수정사항이 생길 수 있습니다. </blockquote>
  <blockquote>해당 포스팅은 KAIST교육을 바탕으로 하며 이해에 필요한 추가적인 정보를 덧붙였습니다.<br/>
  영상과 강의자료는 배포가 불가하기에 공유가 불가하면 포스팅에 사용한 자료와 이미지는 개인적으로 복습하며 만들었습니다. </blockquote>
  <blockquote> 공학이 뭐 그렇듯 용어들은 보통 영어로 기술합니다.<br/>
    블로그에서는 되도록이면 용어를 한글과 영어 두개 다 쓰겠지만<br/>
    발전을 위해서는익숙해지는게 정신건강에 편합니다.
  </blockquote>
  <hr/>
</div>
