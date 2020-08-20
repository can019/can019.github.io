---
title: "[KAIST AI 교육 :: 데이터 분석 및 예측] 1"
date: 2020-08-18 20:15:30 -0400
categories: MachineLearning DataAnalyze
---
# 머신러닝이란?

<hr/>
<div style = "font-size :0.8em">
  <div>
    <h3 style = "font-size :1.2em"> 머신러닝이란?</h3><br/>
    <div style = "margin-left : 30px">
      우리말로 하자면 기계학습으로 경험(학습)을 통해 자동으로 개선시키는 컴퓨터 알고리즘입니다.<br/>
      크게 지도학습, 비지도 학습, 강화학습 3가지로 분류됩니다.<br/><br/>
      <i style = "font-size : 0.9em">강화학습을 지도학습의 하위 개념으로 보아 지도학습, 비지도학습 2개의 분류로 보기도 합니다.</i>
    </div>
  </div>

  <div>
    <h3 style = "font-size :1.2em"> 1. 지도학습(supervised learning)</h3><br/>
    <div style = "margin-left : 30px">
      <b>data와 label을 모두 제공하여 학습시킨다.</b><br/><br/>

      x값과 y값을 모두 제공. 이 때 x는 data, y는 label이라 합니다.<br/><br/>
      ex :: [wx1 + b] = [y1]에서 [wx1 + b] 는 data, [y1] 은 label<br/>
      지도학습은 회귀(Regression)과 분류(Classification)로 나뉩니다.<br/><br/>
      <i style = "font-size : 0.9em">대부분 분류와 회귀로 나뉘지만 object detection, sequence generator과 같은 변종도 존재합니다.</i><br/><br/>

      <b>- 회귀(Regression)</b><br/><br/>
      <div style = "margin-left : 30px">
        학습한 data를 바탕으로 연속된 값을 추정하는 방식입니다.<br/><br/>
        학습으로 얻어진 H(x)를 통해 특정 x일 때 y를 예측하고자 할 때 사용합니다.<br/>
        ex :: 내가 3만원을 벌려면 몇시간 일해야하니?  뛰어서 3km가려면 얼마나 걸리니? 와 같은 문제를 해결하고자 할 때 사용합니다.<br/><br/>
        <br/>
        회귀의 종류에는 linear regression, linear regression을 sigmoid(시그모이드)와 결합하여 보완한 logisitic regression 등이 있습니다.<br/><br/>
      </div>
      <b>- 분류(Classification)</b><br/><br/>
        <div style = "margin-left : 30px">
        말 그대로 분류를 하는 겁니다.
        이 분류는 다시 Binary Classification(이진 분류)와 Multi-label Classification(다중 분류)로 나뉩니다.<br/><br/>
        <b>- Binary Classification(이진 분류)</b><br/><br/>
        <div style = "margin-left : 30px">
          Binary. 말 그 대로 Yes or No 입니다.<br/>
          Q : 이거 강아지니?  <br/>
          A : 예 아니오 <br/><br/>
          위 상황과 같은 case가 이진 분류입니다.
          분류의 경우 실수인 결과값을 반올림 하는데 이진 분류의 경우 0 또는 1로 내리거나 올립니다.<br/><br/>
          <i>강아지니 아니니 이 문제의 output이 0.4775 0.677..등으로 나옵니다. 이 때 0.5를 기준으로 위는 1로 아래는 0으로 때립니다. </i><br/><br/>
        </div>
        <b>- Multi-label Classification(다중 분류)</b><br/><br/>
        <div style = "margin-left : 30px">
          이진 분류에서 case가 여러가지로 나뉜 것입니다.<br/><br/>
          대표적인 예로  이 학생의 성적이 A인지 B인지 C인지 분류하는 경우가 있습니다.

        </div>
      </div>
    </div>
</div>
<div>
  <h3 style = "font-size :1.2em"> 2. 비지도학습(unsupervised learning)</h3>
  <div style = "margin-left : 30px">
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
      <div style = "margin-left : 30px"></div>
      이득과 손해 두가지 reward를 두며 이득은 최대로, 손해는 최소로 두는 학습법입니다.<br><br>
      reward의 가중치를 최대로 하는 것이 목표이며 최적의 동작을 찾고자 하는 분야에서 사용합니다.
      대표적인 예는 알파고입니다.
  </div>
  <div>
    <h3 style = "font-size :1.2em"> 준지도학습(semi-supervised learning)</h3>
    <div style = "margin-left : 30px">
      <b>지도학습과 비지도학습을 섞는다</b><br/>
      하이브리드 입니다.

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
<div/>