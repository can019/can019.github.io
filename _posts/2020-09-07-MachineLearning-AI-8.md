---
title: "[MachineLearning 8] 다중 분류 "
date: 2020-09-07 10:22:15 -0400
categories: MachineLearning DataAnalyze
---
## 다중 분류(multiple classification)

<div style = "font-size : 0.8em"><!--biggest-->
  <a href="https://can019.github.io/machinelearning/dataanalyze/MachineLearning-AI-7/">지난 포스팅</a>
  <div><!--main-->
    <div><!--major1-->
      <h3 style = "font-size :1.2em">다중 분류</h3><!--title of major1-->
        <div style = "margin-left : 3%"><!--Article of major1-->
          이름에서 알 수 있듯 다중 분류는 dataSet을 여러가지 set으로 분류하는 것입니다. <br><br>

          <img src="/assets/photos/machineLearning8/linear_divide.png" width="400px"> <br>
          위 그림처럼 3개의 그룹이 있다면 3개의 선이 찾아지는 것이죠. <br>
          <i style = "font-size : 0.9em">편의를 위해 직선으로 표현했지만 실제론 직선이 아닌 식이 도출됩니다.<br>
          로지스틱 회귀를 안다면 당연한 소리겠지만요</i><br><br>
          <img src="/assets/mathmatical notation/multiple classification with sigmoid matrix.png"><br><br>
          이진 분류와 같은 방법으로 행렬 연산값 각각을 sigmoid로 변환할 수 있지만, <br><br>
          <img src="/assets/mathmatical notation/multiple classification with softmax.png"> <br><br>
          각각의 식에 sigmoid를 취하는 대신 소프트맥스(soft-max)라는 함수로 한꺼번에 인코딩을 해줍니다. <br><br>
          인코딩 후 나온 probability를 <b>'ONE-HOT' Encoding</b>을 통하여 1이나 0으로 인코딩해줍니다. <br>
           <i style = "font-size : 0.9em">ONE-HOT Encoding은 probability중 가장 높은 값을 1로, 나머지 값을 0으로 인코딩합니다. </i>
          <hr>
          <div><!--major1-->
            <h3 style = "font-size :1.2em">소프트맥스(soft-max)</h3><!--title of child1 of major1-->
              <div style = "margin-left : 3%"><!--Article of child1 of major1-->
                소프트맥스는 시그모이드를 일반화한 함수로 <br>
                n차원 data에서 해당 data들이 정답일 확률을 모두 더한 값이 1이되는 함수입니다.<br><br>
                쉽게 말하면 'feature가 n개인 dataSet이 있을 때 <br>
                각 <b>feature가 정답일 확률을 더한 값이 1</b>이되는 함수'라고 말할 수 있습니다.<br><br>

                수식으로 살펴보면<br><br>
                <img src="https://latex.codecogs.com/png.latex?p_{i} = \frac{e^{z_{i}}}{\sum_{j}^{k}e^{z_{j}}}" title="p_{i} = \frac{e^{x_{i}}}{\sum_{j}^{k}e^{x_{j}}}"/><br><br>
                <img src="https://latex.codecogs.com/png.latex?z=w^{x}" title="z=W^{T}X"/>이므로 <img src="https://latex.codecogs.com/png.latex?z_{i}" title="z_{i}">는 <br>
                연산된 행렬곱에서 i번째 값을 말합니다. <br><br>
              </div><!--article of child1 of major1-->
              <hr>
            </div><!--child1 of major1-->
            <div><!--major1-->
              <h3 style = "font-size :1.2em">비용함수</h3><!--title of child1 of major1-->
                <div style = "margin-left : 3%"><!--Article of child1 of major1-->
                  시그모이드와 마찬가지로 소프트맥스를 통한 비용함수 역시 <b>Cross Entropy</b>를 사용합니다.<br><br>
                  <img src="https://latex.codecogs.com/png.latex?D(S,L) = -\sum_{i}^{}L_{i}log(s_{i}) \: \: S = S(y),\,L = Y " title="D(S,L) = -\sum_{i}^{}L_{i}log(s_{i}) \: \: S = S(y),\,L = Y " /><br><br>
                  <img src="https://latex.codecogs.com/png.latex?S(y)" title="S(y)"/>는 소프트맥스를 거져 변환된 probability, 즉 <img src="https://latex.codecogs.com/png.latex?\hat{y}" title="\hat{y}"/>이며<br><br>
                  <img src="https://latex.codecogs.com/png.latex?L=y" title="L=y"/>는 1 or 0의 값으로 label값입니다.<br><br>
                </div><!--article of child1 of major1-->
              </div><!--child1 of major1-->
        </div><!--article of major1-->
      </div><!--major1-->
  </div><!--main-->
  <hr>
  <br>
  <div><!--<blockquote-->
    <blockquote>
      공부하며 작성하는 포스팅이기 때문에 수정사항이 생길 수 있습니다.
    </blockquote>
    <blockquote>
      해당 포스팅은 KAIST교육을 바탕으로 하며 이해에 필요한 추가적인 정보를 덧붙였습니다.<br/>
      영상과 강의자료는 배포가 불가하기에 공유가 불가하며 포스팅에 사용한 자료와 이미지는 개인적으로 복습하며 만들었습니다.
    </blockquote>
  	<blockquote>
      공학이 뭐 그렇듯 용어들은 보통 영어로 기술합니다.<br/>
   	  블로그에서는 되도록이면 용어를 한글과 영어 두개 다 쓰겠지만<br/>
   	  발전을 위해서는익숙해지는게 정신건강에 편합니다.
    </blockquote>
  </div><!--<blockquote-->
</div><!--biggest-->
