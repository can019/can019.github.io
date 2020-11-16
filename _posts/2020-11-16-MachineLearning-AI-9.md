---
title: "[MachineLearning 9] K-NN Classifier "
date: 2020-11-16 16:19:50 -0400
categories: MachineLearning DataAnalyze
---
## K-NN Classifier

<div style = "font-size : 0.8em"><!--biggest-->
  <a href="https://can019.github.io/machinelearning/dataanalyze/MachineLearning-AI-8/">지난 포스팅</a>
  <div><!--main-->
    <div><!--major1-->
      <h3 style = "font-size :1.2em">K-NN Classifier</h3><!--title of major1-->
        <div style = "margin-left : 3%"><!--Article of major1-->
          원래 순서상 로지스틱 회귀 이전에 다루는게 맞으나 <br>
          부득이하게 다음 포스팅으로 작성하게 되었습니다. <br><br>

          K-NN Classifier은 정말 간단한 분류기입니다. <br>
          훈련 샘플 중 x에 가장 가까운 k개를 찾고, <br>

          찾은 k개들의 부류를 조사하여 가장 빈도가 높은 빈도를 x의 부류로 판단합니다.<br><br>
          예를 들어 X1과 가장 가까운 점 5개를 조사했을 때 <br>
          class1인 점이 3개, class2인 점이 1개, class3인 점이 1개라면 <br>
          x를 class1로 분류하는 것이죠. <br><br>

          이 때 k는 3이상의 홀수로 합니다. <br><br>
          이는 정말 당순하게 짝수일 경우 <br>
          class1이 2개, class2가 2개인 경우 분류가 안되기 때문입니다. <br><br>


        </div><!--article of major1-->
      </div><!--major1-->
  </div><!--main-->
  <hr>
  <br>
  <div><!--<blockquote-->
    <blockquote>
      공부하며 작성하는 포스팅이기 때문에 수정사항이 생길 수 있습니다.
    </blockquote>
  </div><!--<blockquote-->
</div><!--biggest-->
