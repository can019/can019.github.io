---
title: "[MachineLearning 1] 머신러닝이란?"
date: 2020-08-18 20:15:30 -0400
categories: MachineLearning DataAnalyze
---

## 머신러닝

<div style = "font-size :0.8em">
  <div>
    <h3 style = "font-size :1.2em"> 머신러닝</h3><br/>
    <div style = "margin-left : 3%">
      우리말로 하자면 기계학습으로 경험(학습)을 통해 자동으로 개선시키는 컴퓨터 알고리즘입니다.<br/>
      인간이 지식을 통해 학습을 하는 것과 다르게 기계는 데이터를 통해 학습을 합니다.<br><br>

      이 때 인간과 다르게 기계는 하나의 식(그래프)을 학습결과로 얻습니다. <br><br>
      이 식은 데이터들을 설명할 수 있는 식으로 1차함수, 2차함수가 될 수도 있고 아주 복잡한 식이 되기도 합니다. <br><br>
      <hr>
      <div>
        <h3 style = "font-size :1.2em"> 모델</h3><br/>
        <div style = "margin-left : 3%">

          기계학습시 컴퓨터에게 데이터만 전달한다고 컴퓨터가 알아서 최적의 식을 찾아주진 못합니다 <br>
          적어도 식이 1차가 될지, 2차가될지 아니면 어떠한 복잡한 식이 될지 개형정도는 알려줘야합니다 <br><br>

          그래프의 개형과 데이터를 컴퓨터에게 알려주면 컴퓨터는 데이터들을 통해 뼈대만 있는 식의 계수들을 찾아내는 것이죠. <br><br>

          즉, 기계가 하는 일은 데이터를 통해 <b>최적의 계수(매개변수)</b>(기울기, y절편 등..)을 찾아내는 것이라고 말할 수 있습니다. <br><br>

          그렇다면 사람이 해주어야 하는 일은 <b>학습시 사용할 적합한 개형을 설계</b>하는 것이라는 것을 알 수 있습니다. <br><br>

          하지만 어떠한 개형이 데이터를 잘 설명할지 알기 어려운 경우가 필연적으로 발생합니다. <br><br>

          따라서 훈련 시 다양한 개형의 설계함수를 훈련시키고, 이 훈련시킨 함수들 중 가장 적합한 식을 결과로 채택합니다. <br><br>

          이 때 훈련시킨 함수들을 <b>'모델 집합'</b>이라고 하며, <br>훈련시킨 함수 또는 훈련시키기 전의 뼈대만 있는 식을 <b>'모델'</b>이라고 합니다 <br><br><br>


          <ul>
            <li>'모델(또는 모델 함수)로 1차함수를 선택했다'</li>
            <li>'모델집합에서 1번 모델이 적합한 것 같다'</li>
          </ul>
          <hr>
          <div>
            <h3 style = "font-size :1.2em"> 바이어스와 분산</h3><br/>
            <div style = "margin-left : 3%">
              <img src = "/assets/photos/machineLearning1/bias_dispersion.png" ><br><br>
              바이어스는 예측값이 정답과 가까울수록 낮고,
              분산은 예측값들이 몰려있을수록 높습니다. <br><br>

              따라서 바이어스가 높다는 것은 모델의 정답률이 떨어진다고 볼 수 있습니다.<br><br>

              바이어스가 낮고 분산이 높은 모델이 이상적인 모델이지만<br>
              바이어스와 분산은 트레이드오프 관계이기 때문에 <br>
              바이어스와 분산 둘다 잡는 것은 불가능합니다. <br><br>

              따라서 바이어스의 희생을 최소로 유지하며 분산을 최대로 낮추는 방향으로 모델을 짜야합니다.<br><br>

            </div>
          </div>

        </div>
        <hr>
      </div>
      <div>
        <h3 style = "font-size :1.2em"> 데이터</h3><br/>
        <div style = "margin-left : 3%">

          데이터는 훈련 집합, 검증 집합, 테스트 집합으로 나뉘며 훈련 집합은 모델을 만들어내는데,<br>
          검증 집합은 훈련으로 만들어진 모델을 검증하는데, 테스트 집합은 모델의 성능을 측정하는데 사용됩니다. <br><br>

          검증 집합의 목적은 overfitting과 underfitting을 피하기 위한 집합,<br><br>
          테스트 집합은 성능 측정을 위한 집합으로 <br>
          검증 집합은 답까지 포함된 데이터, 테스트 집합은 답이 없는 데이터를 사용합니다. <br><br>

          <b>  훈련 -> 검증 -> 모델선택 -> 테스트 </b><br>
          <hr>
          <div>
            <h3 style = "font-size :1.2em"> UnderFitting(과소적합), OverFitting(과잉적합)</h3><br/>
            <div style = "margin-left : 3%">
              과소 적합은 너무 단순한 모델을 사용하여 데이터를 잘 설명하지 못하는 경우,<br>
              과잉 적합은 너무 높은 모델을 채택하여 훈련 집합에는 높은 정답률을 보이나 <br>
              테스트 집합이나 실세계 데이터에 대해 낮은 정답률을 보이는 경우를 말합니다. <br><br>

            </div>
            <hr>
          </div>
          <div>
            <h3 style = "font-size :1.2em">검증 집합을 사용한 모델링</h3>
            <div style = "margin-left : 3%">
              <div>
                <h3 style = "font-size :1.2em"> 1. 검증 집합을 이용한 모델 선택</h3><br/>
                <div style = "margin-left : 3%">
                  <b>훈련 집합, 테스트 집합과 다른 별도의 검증 집합을 가진 상황</b>

                  모든 자원이 충분하므로 고려할 점이 없는 경우입니다. <br><br>
                  <ol>
                    <li>모델을 훈련집합으로 학습.</li>
                    <li>검증 집합으로 학습된 모델의 성능 측정.</li>
                    <li>1, 2를 반복하여 생성된 모델 집합들 중 가장 높은 성능을 보인 모델 선택.</li>
                    <li>테스트 집합으로 선택된 모델의 성능 측정.</li>
                  </ol>
                  <br>

                </div>
                <hr>
              </div>
              <div>
                <h3 style = "font-size :1.2em"> 2. 교차 검증(cross validation)</h3><br/>
                <div style = "margin-left : 3%">
                  <b>별도의 검증 집합이 없는 상황</b><br>
                  <b>훈련 집합을 등분, 학습과 평과 과정을 여러번 반복한 후 평균 사용</b><br><br>
                  cross validation은 모든 데이터가 1회 이상 훈련 집합, 검증 집합으로 사용됩니다. <br><br>

                  훈련 집합을 n개의 집합으로 등분합니다. <br><br>
                  n개의 집합 중 1번째 집합을 검증 집합, 나머지를 훈련 집합으로 선택한 후 훈련합니다.<br><br>
                  그다음 2번째 집합을 검증 집합, 나머지를 훈련집합으로 선택한 후 훈련합니다. <br><br>
                  이러한 방식으로 k번째 집합을 검증 집합으로 한 훈련까지 모두 진행했다면 모델 성능을 측정하고 <br>
                  모델 선택, 그 후 테스트 집합으로 모델 성능을 측정합니다. <br><br><br>

                  <ol>
                    <li>훈련 집합을 n개의 그룹으로 등분</li>
                    <li>i번째 그룹을 검증 집합, 나머지를 (n-i)개 그룹을 훈련 집합으로 선택. 이 때 i = 1 ~ n, i++ </li>
                    <li>n개의 성능의 <b>평균</b>을 해당 모델의 성능으로 함.</li>
                    <li>모델 중 가장 높은 성능을 보인 모델을 선택.</li>
                    <li>테스트 집합으로 선택된 모델의 성능 측정.</li>
                  </ol>

                  <i style = "font-size : 0.9em">1, 2, 3은 하나의 모델을 모델링하는 과정.</i><br>
                  <hr>
                  <div>
                    <h3 style = "font-size :1.2em"> 2-1. Leave-one-out cross validation</h3><br/>
                    <div style = "margin-left : 3%">
                    <b>주어진 데이터가 극한으로 적은 상황</b><br>

                    cross validation은 데이터를 n개의 집합으로 나누고 하나를 검증 집합, 나머지를 훈련 집합으로 채택하였습니다.<br><br>
                    Leave-one-out cross validation은 집합을 나누지 않고 <b>단 하나의 데이터를 검증 집합, 나머지를 훈련집합으로 채택</b>합니다.<br><br>

                    현재는 수집된 데이터가 많고 구하기 쉽기 때문에 <br>
                    Leave-one-out cross validation을 채택하는 경우는 거의 없으나, <br><br>

                    초창기때에는 데이터가 부족하여 Leave-one-out cross validation을 많이 사용하였습니다.<br><br>
                    </div>
                  </div>
                </div>
                <hr>
              </div>
              <div>
                <h3 style = "font-size :1.2em"> 3. 부트스트랩(boot strap)</h3>
                <div style = "margin-left : 3%">
                  <b>별도의 검증 집합이 없는 상황</b><br>
                  <b>난수를 이용한 샘플링 반복</b>

                  cross validation과 비슷합니다.<br><br>
                  차이는 훈련 집합을 Random하게 뽑는 것과, 반복 횟수를 정하는것 외엔 없습니다.

                  <ol>
                    <li>훈련 집합 'X'에서 n개의 데이터를 뽑아 새로운 훈련 집합 'X1'으로 삼음. 'X1'에는 중복된 데이터가 존재 가능.</li>
                    <li>'X1'을 훈련모델로 채택하여 T번 학습. </li>
                    <li>T개의 성능의 평균을 해당 모델의 성능으로 함.</li>
                    <li>가장 높은 성능을 보인 모델을 선택.</li>
                    <li>테스트 집합으로 선택된 모델의 성능 측정.</li>
                  </ol>
                </div>
              </div>
            </div>
          </div>
        </div>
        <hr>
      </div>
    </div>
  </div>
  <div>
    <h3 style = "font-size :1.2em"> 머신러닝의 종류</h3>
    <div style = "margin-left : 3%">
      크게 지도학습, 비지도 학습, 강화학습 3가지로 분류됩니다.<br/><br/>
      <i style = "font-size : 0.9em">강화학습을 지도학습의 하위 개념으로 보아 지도학습, 비지도학습 2개의 분류로 보기도 합니다.</i><br>
      <div>
        <h3 style = "font-size :1.2em"> 1. 지도학습(supervised learning)</h3><br/>
        <div style = "margin-left : 3%">
          <b>data와 label을 모두 제공하여 학습시킨다.</b><br/><br/>

          x값과 y값을 모두 제공. 이 때 x는 data, y는 label이라 합니다.<br/><br/>
          ex :: [wx1 + b] = [y1]에서 [wx1 + b] 는 data, [y1] 은 label<br/>
          지도학습은 회귀(Regression)과 분류(Classification)로 나뉩니다.<br/><br/>
          <i style = "font-size : 0.9em">대부분 분류와 회귀로 나뉘지만 object detection, sequence generator과 같은 변종도 존재합니다.</i><br/><br/>

          <b>- 회귀(Regression)</b><br/><br/>
          <div style = "margin-left : 3%">
            학습한 data를 바탕으로 연속된 값을 추정하는 방식입니다.<br/><br/>
            학습으로 얻어진 H(x)를 통해 특정 x일 때 y를 예측하고자 할 때 사용합니다.<br/>
            ex :: 내가 3만원을 벌려면 몇시간 일해야하니?  뛰어서 3km가려면 얼마나 걸리니? 와 같은 문제를 해결하고자 할 때 사용합니다.<br/><br/>
            <br/>
            회귀의 종류에는 linear regression, linear regression을 sigmoid(시그모이드)와 결합하여 보완한 logisitic regression 등이 있습니다.<br/><br/>
          </div>
          <b>- 분류(Classification)</b><br/><br/>
            <div style = "margin-left : 3%">
            말 그대로 분류를 하는 겁니다.
            이 분류는 다시 Binary Classification(이진 분류)와 Multi-label Classification(다중 분류)로 나뉩니다.<br/><br/>
            <b>- Binary Classification(이진 분류)</b><br/><br/>
            <div style = "margin-left : 3%">
              Binary. 말 그 대로 Yes or No 입니다.<br/>
              Q : 이거 강아지니?  <br/>
              A : 예 아니오 <br/><br/>
              위 상황과 같은 case가 이진 분류입니다.
              분류의 경우 실수인 결과값을 반올림 하는데 이진 분류의 경우 0 또는 1로 내리거나 올립니다.<br/><br/>
              <i>강아지니 아니니 이 문제의 output이 0.4775 0.677..등으로 나옵니다. 이 때 0.5를 기준으로 위는 1로 아래는 0으로 때립니다. </i><br/><br/>
            </div>
            <b>- Multi-label Classification(다중 분류)</b><br/><br/>
            <div style = "margin-left : 3%">
              이진 분류에서 case가 여러가지로 나뉜 것입니다.<br/><br/>
              대표적인 예로  이 학생의 성적이 A인지 B인지 C인지 분류하는 경우가 있습니다.

            </div>
          </div>
        </div>
    </div>
    <div>
      <h3 style = "font-size :1.2em"> 2. 비지도학습(unsupervised learning)</h3>
      <div style = "margin-left : 3%">
        <b>data만 제공하여 학습시킨다.</b><br/><br/>
        data만 존재하고 label이 존재하지 않는 경우입니다.<br><br>

        data의 상관관계(사전지식 등)를 모를 경우 유용합니다. 우리가 직관적으로 알 수 없는, 서로 상관관계가 없어보이는 data들 속에서<br>
        유의미한 ouput을 얻을 수 있습니다.<br><br>
        가장 대표적인 예가 cluster(군집화)입니다.
        lable(결과값) 없이 강아지, 사자, 비둘기 등의 data를 input으로 넣었을 때 컴퓨터는 이것이 강아지인지 사자인지 비둘기인지 <br>
        구분하지 못합니다.<br><br>
        다만 이것은 다리가 두개다, 네개다 정도까진 나눌 수 있습니다.<br><br>
      </div>

      </div>
      <div>
        <h3 style = "font-size :1.2em"> 3. 강화학습(reinforcement learning)</h3>
        <b>이득은 최대로, 손해는 최소로</b><br/><br/>
          <div style = "margin-left : 3%"></div>
          이득과 손해 두가지 reward를 두며 이득은 최대로, 손해는 최소로 두는 학습법입니다.<br><br>
          reward의 가중치를 최대로 하는 것이 목표이며 최적의 동작을 찾고자 하는 분야에서 사용합니다.
          대표적인 예는 알파고입니다.
      </div>
      <div>
        <h3 style = "font-size :1.2em"> 준지도학습(semi-supervised learning)</h3>
        <div style = "margin-left : 3%">
          <b>지도학습과 비지도학습을 섞는다</b><br/>
          하이브리드 입니다.

        </div>

      </div>
    </div>
  </div>



  <div>
  </div>
  <hr/>
  <br/><br/> **미완성인 포스팅입니다.**
  <br/><br/> 공부하며 작성하는 포스팅이기 때문에 수정사항이 생길 수 있습니다.
  <blockquote> 공학이 뭐 그렇듯 용어들은 보통 영어로 기술합니다.<br/>
    블로그에서는 되도록이면 용어를 한글과 영어 두개 다 쓰겠지만<br/>
    발전을 위해서는익숙해지는게 정신건강에 편합니다.
  </blockquote>
  <hr/>
</div>
