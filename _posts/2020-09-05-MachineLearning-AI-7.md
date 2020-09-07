---
title: "[MachineLearning 7] 이진 분류 "
date: 2020-09-05 11:14:15 -0400
categories: MachineLearning DataAnalyze
---
## 이진 분류(binary classification)

<div style = "font-size : 0.8em"><!--biggest-->
  <a href="https://can019.github.io/machinelearning/dataanalyze/MachineLearning-AI-6/">지난 포스팅</a>
  <div><!--main-->
    <div><!--major1-->
      <h3 style = "font-size :1.2em">이진 분류</h3><!--title of major1-->
      <div style = "margin-left : 3%"><!--Article of major1-->
        두 집단을 나누는 최적의 식을 찾아내는 것이 이진 분류입니다. <br><br>
        <img src="/assets/photos/machineLearning7/conversion.png" width="550px"><br><br>
        선형식 z를 sigmoid 함수로 인코딩하여 0, 1 사이의 결과값을 얻어냅니다. <br><br>

        그리고 위와 같이 어떠한 식을 인코딩해주는 함수를 활성화함수라고 합니다.<br><br>
        활성화 함수는 나중에 신경망에서 이야기 할 예정이니 지금은 가볍게 '변환기' 느낌으로 생각하시면 됩니다.<br><br>
        그리고 data(x값)을 추론된 모델에 대입하여 나온 y값이 0.5이상이라면 1, 이하라면 0으로 내려 참과 거짓을 판별합니다.<br><br>
        <img src="https://latex.codecogs.com/png.latex?z = wx+b" title="z = wx+b"/>, <img src="https://latex.codecogs.com/png.latex?0\leq g(x)\leq 1 " title="0\leq g(x)\leq 1"/><br>
        <hr>
        <div><!--child1 of major1-->
          <h3 style = "font-size :1.2em">시그모이드(sigmoid)</h3><!--title of child1 of major1-->
          <div style = "margin-left : 3%"><!--article of child1 of major1-->
            <div><!--grandchild1 of major1-->
              <h3 style = "font-size :1.2em">시그모이드를 사용하는 이유</h3><!--title of grandchild1 of major1-->
              <div style = "margin-left : 3%"><!--article of grandchild1 of major1-->
                그래프 개형이 'S'자와 같아 시그모이드라는 이름이 붙게 되었습니다. <br><br>
                시그모이드를 사용하는 이유는 다음과 같습니다. <br><br>
                **가중치는 계산 및 훈련으로 얻어진 것이 아닌 극단적인 비교를 위한 임의의 값입니다**<br><br>
                <img src="/assets/photos/machineLearning7/wx+b_1.png" width="550px"><br><br>
                훈련 결과로 H(x) = 0.15x라는 선형모델을 얻었습니다. <br>
                H(1) = 0.15 H(2) = 0.3 H(3) = 0.45 => false, H(6) = 0.9 H(7) = 1.05 => true로 잘 분류가 됩니다.<br><br>
                <img src="/assets/photos/machineLearning7/wx+b_2.png" width="550px"><br><br>
                그런데 새로운 data가 들어오며 선형모델이 H(x) = 0.0525x로 변경되었습니다.<br><br>
                이 때 6과 7은 true이므로 H(6), H(7)은 0.5이상이 나와야하나 <br>
                H(6) = 0.315 H(7) = 0.3675 => 0.5이하로 둘 다 false로 분류되었습니다<br><br>

                <img src="/assets/photos/machineLearning7/sigmoid.png" width="550px"><br>
                이러한 이유로 선형식을 그대로 사용하지 않고 sigmoid라는 활성함수로 한번 인코딩 해주는 것입니다.<br><br>
                (활성함수는 비선형함수를 사용합니다.)

              </div><!--article of grandchild1 of major1-->
            </div><!--grandchild1 of major1-->
            <div><!--grandchild2 of major1-->
              <h3 style = "font-size :1.2em">유도</h3><!--title of grandchild2 of major1-->
              <div style = "margin-left : 3%"><!--article of grandchild2 of major1-->
                시그모이드는 '비율'에 관한 함수입니다.<br>
                이 함수를 odd(p)라고 하며 odd(p) = p/1-p 로 정의됩니다. <br><br>
                그리고 odd(p)의 범위가 0~+inf이므로 <br><br>
                -inf~+inf로 변환해주기 위해 ln를 취해줍니다. <br>
                ln(p(x)) = wx+b <br>
                이후 식을 p에대해 정리해주면 <img src="https://latex.codecogs.com/png.latex?p(x) = \frac{1}{1+e^{-x}}" title="p(x) = \frac{1}{1+e^{-x}}"/><br><br>
                <img src="https://latex.codecogs.com/png.latex?sigmoid = g(x) = \frac{1}{1+e^{-x}}" title="sigmoid = g(x) = \frac{1}{1+e^{-x}}"/><br><br>
                <i style = "font-size : 0.9em">또한 통계에서 근사값을 구하는 경우 통상 ln을 취한다고 합니다. - 통계학과 친구 -</i><br><br>

                분류로 돌아오겠습니다.<br>
                데이터가 X, 이진 분류 모델을 H(X)라고 할 때 <img src="https://latex.codecogs.com/png.latex?H(X) = g(z)" title="H(X) = g(z)"/>라고 할 수 있습니다. <br><br>
                이 때   <img src="https://latex.codecogs.com/png.latex?z = WX" title="z = WX"/>이므로 식을 다시 쓰면 <br><br>
                <img src="https://latex.codecogs.com/png.latex?H(X) = \frac{1}{1+e^{-W^{T}X}}" title="H(X) = \frac{1}{1+e^{-W^{T}X}}"/>가 됩니다.<br><br>
                <img src="https://latex.codecogs.com/png.latex?-W^{T}X" title="-W^{T}X"/>에서 T는 Transpose이며, 행렬곱을 위해 바꿔줍니다. <br><br>
                다중 선형 회귀에서 행렬곱을 위해 XW해주었던 것을 생각하면 되겠습니다.<br><br>

              </div><!--article of grandchild2 of major1-->
            </div><!--grandchild2 of major1-->
          </div><!--article of child1 of major1-->
        </div><!--child1 of major1-->
        <hr>
        <div><!--child2 of major1-->
          <h3 style = "font-size :1.2em">비용함수</h3><!--title of child2 of major1-->
          <div style = "margin-left : 3%"><!--article of child2 of major1-->
            H(x)가 변경되었으므로 비용함수 역시 형태가 변경됩니다.<br/><br/>
            선형회귀법과 같이 거리의 제곱으로 cost함수를 만드게 된다면<br/>
            <img src="/assets/photos/machineLearning7/cost_mse.png" width="550px"><br/>
            이 그래프 처럼 local minima가 2개이상 발생되며 <br>
            심한경우 그래프가 포도송이모양으로 형성되기도 합니다.<br/><br/>

            이 경우경사하강법을 사용하기 어렵기 때문에 새로운 비용 함수를 설계합니다.<br/><br/>

            <img src="https://latex.codecogs.com/png.latex?H(X) = \frac{1}{1+e^{-W^{T}X}}" title="H(X) = \frac{1}{1+e^{-W^{T}X}}"/>일 때<br><br>
            한점에서의 cost는 <img src="https://latex.codecogs.com/png.latex?c(H(x),y) =\left\{\begin{matrix}-log(H(x)) : y=1\\ -log(1-H(x)) : y=0\end{matrix}\right." title="c(H(x),y) =\left\{\begin{matrix}-log(H(x)) : y=1\\ -log(1-H(x)) : y=0\end{matrix}\right."/>이므로<br><br>
            이분화된 식을 하나의 식으로 합치면<br/>
            <img src="https://latex.codecogs.com/png.latex?c(H(x),y) = -ylog(H(x)) - (1-y)log(1-H(x))" title="c(H(x),y) = -ylog(H(x)) - (1-y)log(1-H(x))"/>가 됩니다. <br><br>

            따라서 cost의 평균은 <img src="https://latex.codecogs.com/png.latex?cost(w) = \frac{1}{m}\sum_{1}^{m}(-ylog(H(x)) - (1-y)log(1-H(x)))" title="cost(w) = \frac{1}{m}\sum_{1}^{m}(-ylog(H(x)) - (1-y)log(1-H(x)))"/>가 됩니다.<br><br>

            <i style = "font-size : 0.9em"> y = 1일 때 -log(z)는 왼쪽에서 떨어지는 곡선<br/>
            y = 0일 때 -log(1-z)는 오른쪽에서 떨어지는 곡선으로 합치게 되면 2차함수 꼴의 부드러운 함수가 됩니다.</i><br/><br/>

          </div><!--article of child2 of major1-->
        </div><!--child2 of major1-->
        <hr>
      </div><!--Article of major1-->
  </div><!--main-->

  <hr>
  ***미완성 포스팅*** <br>
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
