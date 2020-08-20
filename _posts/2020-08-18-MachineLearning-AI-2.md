---
title: "[KAIST AI 교육 :: 데이터 분석 및 예측] 2"
date: 2020-08-19 01:56:30 -0400
categories: MachineLearning DataAnalyze
---
# 선형회귀와 경사하강법

<hr/>
<div style = "font-size :0.8em">
  <div>
    <h3 style = "font-size :1.2em"> 선형?</h3><br/>
    <div style = "margin-left : 30px">

      공대생이라면 절대 모를 리 없는 '선형'이지만 요즘 머신러닝이 인기가 많기에 비전공자들도
      머신러닝을 하기에 조금 설명하자면..<br/><br/>

      선형(linear). 이름에서 유추 할 수 있듯 하나의 직선으로 표현되는 것이고 그러한 성질을 띄는 것을 선형성이라 합니다.<br/><br/>

      엄밀히 이야기 하자면 이론적인 선형성은 vector에서 이야기 되며, vector에 특징 답게 기울기만 같다면 같은 것으로 칩니다.<br/><br/>
      중학교때 배우는 1차함수인 y = ax꼴을 생각하면 됩니다.<br/><br/><br/>
      <i style = "font-size : 0.9em">y절편, 출발점, 길이를 무시한다는 소리입니다.</i><br/><br/>



      <i style = "font-size : 0.9em">선형성은 중첩의 원리를 보장 (ax1+bx2 = a(x1+x2)를 만족)하며 중첩의 원리가 통하는 식들은 직관적이고 예측 가능합니다.<br/>
        더 나아가 선형성이 만족하는 모델은 적용할 수 있는 원리와 공식들이 정말정말정말 많기 때문에<br/>
        논문들에서 내가 만든 모델이 선형성을 띈다는 것을 증명하는데 많은 노력을 가하는 이유입니다.</i><br/><br/><br/>


    </div>
  </div>
  <div>
    <h3 style = "font-size :1.2em"> 회귀(regression)분석</h3><br/>
    <div style = "margin-left : 30px">


      회귀분석이란 다양한 data와 label이 존재할 때 label과 data간에 존재하는 상관관계를 식으로 정의하는 기법입니다.<br><br>
      이 때 식은 회귀모델이라 부르며 학습을 통해 가장 완벽한(오차가 적은) 회귀모델을 추정하는 것이 머신러닝에서의 회귀분석입니다.<br><br>

      회귀모델을 얻어내기 위해서는 data(x값), label(y값 : 결과값), 가설(hypothesis) 이 세가지가 필요합니다.<br>
      가설이란 계수가 모두 미지수인 식으로 1차식이 될 수도 있고 아니면 초월함수꼴이 될 수도 있습니다.<br><br>
      ex :: H(x) = w1x1+b <br><br>
      이렇게 세운 가설과 data, label을 컴퓨터에게 주면 컴퓨터는 data와 label을 설명할 수 있는 H(x)들을 만들어내고<br/><br/>
      그 중 가장 fit한 회귀모델을 얻어냅니다.<br/><br/>

      <i style = "font-size : 0.9em">
      '평균으로의 회귀'.프랜시스 골턴이 처음 주장한 이론으로 극단적이거나 이례적인 결과는 평균 방향으로 되돌아오는 경향을 가진다는 개념입니다.<br><br>
      인류의 평균 키를 A라고 했을 때 아버지가 A보다 크면 아들은 A보다 작고, 아버지가 A보다 작으면 아들은 A보다 크게되는
      관찰 결과에서 비롯됐으며,<br>
      키가 아주 크거나 작거나 모두 세대가 갈수록 평균과 가까워 진다는 이론입니다. <br><br>
      그럼 fit한 모델을 추정하는 것을 왜 회귀라 부르냐??<br/><br/>
      Cost가 회귀하기 때문이죠. Cost에 대한 설명은 아래 선형회귀에서 설명합니다.</i><br/><br/>



    </div>
  </div>
  <div>
    <h3 style = "font-size :1.2em"> 선형회귀</h3><br/>
    <div style = "margin-left : 30px">
      그럼 회귀 중 가장 간단한 단순선형회귀부터 살펴보겠습니다.<br/><br/>
      위에서 예시로 든 H(x)와 같이 y = wx+b꼴의 가설의 형태를 가지는 것이 단순선형회귀입니다.<br/><br/><br/>

      <img src="/assets/photos/20200820_1.png" width="450"><br><br>
      위 그래프를 예로 보겠습니다.<br/>
      파란색 점이 data, label set이라 할 때 이상적인 모델은 파란색 그래프,<br/> 
      주황색과 초록색 그래프는 이상적이지 못한 모델이 됩니다.<br/><br/>
      
      파란색 그래프를 찾아내는 방법으로 가장 먼저 생각할 수 있는 것은 점을 대입하여 w,b 값을 찾아내거나<br/>
      아니면 random한 w, b값을 대입하여 모델은 만들고 그 모델에 다시 data, label을 대입하여 찾아낸 모델이 fit한 모델인지 검사하는 방법이 있겠죠.<br/><br/>
     
      위 방법 두가지 모두 일리있는 말입니다.<br/><br/>
      하지만 현실세계의 데이터들이 모두 하나의 직선위에 있는 이상적은 경우는 없으며<br/>
      저 두가지 방법으로 모델을 찾을 경우 많은 시간이 소요됩니다.<br/><br/>

      그래서 조금 다른 방법으로 접근하고자 합니다.<br/>
      <b>바로 Cost(비용)를 통한 접근 방법입니다.</b><br/><br/>
      이 방법은 정답을 찾는 것이 아닌 <b style ="color : red">'정답에 가장 가까운 답'</b>을 찾는 것입니다.<br/><br/>
      바로 <b style ="color : red">거리</b>를 이용한 방법입니다.<br/><br/>
   
      <img src="/assets/photos/20200820_2.png" width="450"><br><br>
       검정색 점은 data와 label set, 파란색 직선이 임의로 만들어진 모델이라고 할 때<br/>
       거리의 제곱의 합, 즉 빨간 선분의 제곱의 합을 통해 이상적인 모델을 찾습니다.<br/><br/>
       이 때 빨간 선분의 제곱의 합의 평균을 <b>비용(Cost)</b>라고 합니다.<br/><br/>
       

       한 점에서의 거리의 제곱은 <img src="https://latex.codecogs.com/png.latex?(H(x)-y)^{2}" title="(H(x)-y)^{2}" />라고 할 수 있으므로<br/><br/>
       Cost의 정의를 수식으로 나타내면 <img src="https://latex.codecogs.com/png.latex?\frac{1}{m}\sum_{i=1}^{m}(H(x^{i})-y^{i})^{2}" title="\frac{1}{m}\sum_{i=1}^{m}(H(x^{i})-y^{i})^{2}" />가 됩니다.<br/><br/>
       i는 i번째 data, label set을 의미하며 <img src="https://latex.codecogs.com/png.latex?(x^{1},y^{1}),&space;(x^{2},y^{2}),&space;(x^{3},y^{3}),&space;...(x^{1},y^{i})" title="(x^{1},y^{1}), (x^{2},y^{2}), (x^{3},y^{3}), ...(x^{1},y^{i})" /><br/><br/>이 때 m은 data, label set의 갯수를 의미합니다.<br/><br/><br/>
       즉 한마디로 정리하면 Cost의 평균을 통해 가장 fit한 가설(모델)을 찾아내는 것이 선형회귀법입니다.<br/><br/><br/>

      


       만들어진 모델이 파란색 직선, data와 label set이 검정색 점이라고 할 때<br/>
       빨간색 선, 즉 거리의 제곱의 평균







      간단히 말하자면 '회귀모델이 선형식이다'입니다.
      가설의 w1과 b에 수를 대입한 후 data, label을 모델에 대입,<br/><br/>
      이 과정을 무한히 거쳐 가장 fit한 회귀모델을 찾아냅니다.<br><br>
      (물론 w1과 b에 숫자를 계속 넣어가며 최적의 H(x)를 추정하는 것은 비효율적이라 쓰지 않습니다.)
    </div>
  </div>


  <hr/>
  <br/><br/> **미완성인 포스팅입니다.**
   <blockquote> 공부하며 작성하는 포스팅이기 때문에 수정사항이 생길 수 있습니다. </blockquote>
  <blockquote>해당 포스팅은 KAIST교육을 바탕으로 하며 이해에 필요한 추가적인 정보를 덧붙였습니다. </blockquote>
  <blockquote> 공학이 뭐 그렇듯 용어들은 보통 영어로 기술합니다.<br/>
    블로그에서는 되도록이면 용어를 한글과 영어 두개 다 쓰겠지만<br/>
    발전을 위해서는익숙해지는게 정신건강에 편합니다.
  </blockquote>
  <hr/>
</div>
