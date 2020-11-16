---
title: "[MachineLearning 10] SVM "
date: 2020-11-16 16:19:50 -0400
categories: MachineLearning DataAnalyze
---
## SVM

<div style = "font-size : 0.8em"><!--biggest-->
  <a href="https://can019.github.io/machinelearning/dataanalyze/MachineLearning-AI-8/">지난 포스팅</a>
  <div><!--main-->
    <div><!--major1-->
      <h3 style = "font-size :1.2em">SVM</h3><!--title of major1-->
        <div style = "margin-left : 3%"><!--Article of major1-->
          1990년대 신경망의 성능을 능가하여 인기 있는 모델로 부상했습니다. <br><br>
          물론 2000년대 딥러닝이 등장하며 현재는 그렇게까지 인기있는 모델은 아니나 <br><br>
          최근에는 딥러닝과 SVM을 결합하는 경우 좋은 성능을 보이는 경우가 있어<br>
          둘의 결합에 대한 연구가 많이 진행되고 있습니다. <br><br>

          SVM의 초점은 '여백'입니다.<br><br>
          훈련으로 class와 class를 분류하는 모델, 즉, 하나의 식이 도출됩니다.<br><br>
          
          이 식은 2차원에서는 선, 3차원은 평면, 4차원 이상은 초평면이 되지만 <br><br>
          통상 이 식/면을 결정 초평면이라고 부릅니다.<br><br>

          이 때 뽑아낸 결정 초평면과 각 class간 최소 거리가 되는 점(x,label)을 <br><br>

          <b>Support Vector</b>라고 부릅니다. <br><br>

          이 Support Vector와 결정 초평면의 거리가 좁다면, <br>
          <i style = "font-size : 0.9em">쉽게 유도리가 부족하다면</i><br><br>
          추가적으로 들어올 데이터에 대한 예측이 부정확 할 수 있습니다.<br><br>
           
          이에 결정 초평면을 어느정도 떨어뜨려<br> 
          높은 일반화 성능을 뽑아내고자 하는 것이죠. <br><br>

          <img src="/assets/photos/machineLearning10/svm_overfit.jpg"> <br>
          그림으로 보면 바로 이해가 되실겁니다.<br><br>
          '보라색 점선이 아닌 어느정도 여백이 있는 실선을 사용하겠다.' <br><br>
          
          실제 SVM에서는 최적의 W를 찾은 후 b를 margin으로 결정하는 것이 아닌, <br><br>
          분류를 진행할 수 있는 결정초평면 후보를 몇가지 뽑은 후<br>
          결정초평면에 대한 margin 계산,<br><br>
          최적의 결정초평면을 채택합니다.<br><br>
          <div><!--child1 of major1-->
            <h3 style = "font-size :1.2em">선형 SVM</h3><!--title of child1 of major1-->
              <div style = "margin-left : 3%"><!--Article of child1 of major1-->
                  선형 svm의 경우 따져줄 것이 크지 않습니다.<br><br>

                  d(x) = WTX + b = 0인 결정초평면을 구했을 때<br><br>
                  classA는 d(x)>0을, classB는 d(x)<0>을 만족합니다.<br> 
                  <i style = "font-size : 0.9em">0대신 임의의 상수 c를 줘도 같은 결정초평면입니다.</i><br><br>

                  여기서 W는 초평면의 법선 벡터, b는 위치를 나타내며<br>
                  임의의 점 x에서 초평면 까지의 거리 h = |d(x)|/||w||입니다.<br><br>

                  통상 d(x)가 +1, -1 사이 범위는 outlier로 판단, 버려주며<br><br>
                  이렇기에 margin의 영역은 2/||w||로 표현이 됩니다. <br><br>
                  margin의 영역이 커질 수록 새로운 data에 대한 예측률은 올라가며,<br>
                  학습 data에 대한 예측률은 줄어듭니다. <br>

              </div><!--article of child1 of major1-->
            </div><!--child1 of major1-->
        </div><!--article of major1-->

        <div><!--child1 of major1-->
          <h3 style = "font-size :1.2em">비선형 SVM</h3><!--title of child2 of major1-->
            <div style = "margin-left : 3%"><!--Article of child2 of major1-->
              비선형 SVM의 경우 단순히 결정초평면이 비선형인 경우입니다.<br><br>
              비선형 SVM은 매우 복잡하고 어려우며 이것만 따로 구현하는 기업들이 있을 정도기에<br><br>
              자세히 다루지는 않겠습니다.<br>

            </div><!--article of child2 of major1-->
          </div><!--child2 of major1-->
      </div><!--article of major1-->

      <div><!--child3 of major1-->
        <h3 style = "font-size :1.2em">c-부류 SVM SVM</h3><!--title of child3 of major1-->
          <div style = "margin-left : 3%"><!--Article of child3 of major1-->


          </div><!--article of child3 of major1-->
        </div><!--child3 of major1-->
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
