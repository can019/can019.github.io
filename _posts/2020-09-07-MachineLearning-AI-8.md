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
          위 그림처럼 3개의 그룹이 있다면 3개의 선이 찾아지는 것이죠. <br><br>
          <img src="https://latex.codecogs.com/png.latex?\begin{bmatrix}w_{A1}& w_{A2} &w_{A3} \\
w_{B1}&  w_{B2}& w_{B3}\\
 w_{C1}& w_{C2} & w_{C3}
\end{bmatrix}
\begin{bmatrix}
x_{1}\\
x_{2}\\
x_{3}
\end{bmatrix} = \begin{bmatrix}
 w_{A1}x_{1}+w_{A2}x_{1} +w_{A3}x_{1} \\
 w_{B1}x_{2}+ w_{B2}x_{2}+ w_{B3}x_{2}\\
 w_{C1}x_{3}+ w_{C2}x_{3} +w_{C3}x_{3}
\end{bmatrix}
=\begin{bmatrix}
\hat{Y}_{A}\\
\hat{Y}_{B}\\
\hat{Y}_{C}
\end{bmatrix}\begin{matrix}
\rightarrow & <sigmoid>&\rightarrow  lineA\\
\rightarrow & <sigmoid>&\rightarrow lineB\\
\rightarrow & <sigmoid>&\rightarrow lineC
\end{matrix}" title="\begin{bmatrix}
 w_{A1}& w_{A2} &w_{A3} \\
 w_{B1}&  w_{B2}& w_{B3}\\
 w_{C1}& w_{C2} & w_{C3}
\end{bmatrix}
\begin{bmatrix}
x_{1}\\
x_{2}\\
x_{3}
\end{bmatrix} = \begin{bmatrix}
 w_{A1}x_{1}+w_{A2}x_{1} +w_{A3}x_{1} \\
 w_{B1}x_{2}+ w_{B2}x_{2}+ w_{B3}x_{2}\\
 w_{C1}x_{3}+ w_{C2}x_{3} +w_{C3}x_{3}
\end{bmatrix}
=\begin{bmatrix}
\hat{Y}_{A}\\
\hat{Y}_{B}\\
\hat{Y}_{C}
\end{bmatrix}\begin{matrix}
\rightarrow & <sigmoid>&\rightarrow  lineA\\
\rightarrow & <sigmoid>&\rightarrow lineB\\
\rightarrow & <sigmoid>&\rightarrow lineC
\end{matrix}"/><br>
          위 수식처럼 이진 분류와 같은 방법으로 행렬 연산값 각각을 sigmoid로 변환할 수 있지만, <br><br>
          각각에 식에 sigmoid를 취하는 대신 소프트맥스(soft-max)라는 함수로 한꺼번에 인코딩을 해줍니다. <br>

          <div><!--major1-->
            <h3 style = "font-size :1.2em">소프트맥스(soft-max)</h3><!--title of child1 of major1-->
              <div style = "margin-left : 3%"><!--Article of child1 of major1-->
                시그모이드와 마찬가지로 소프트맥스

              </div><!--article of child1 of major1-->
              <hr>
            </div><!--child1 of major1-->
            <div><!--major1-->
              <h3 style = "font-size :1.2em">비용함수</h3><!--title of child1 of major1-->
                <div style = "margin-left : 3%"><!--Article of child1 of major1-->
                  시그모이드와 마찬가지로 소프트맥스를 통한 비용함수 역시 Cross Entropy를 사용합니다.

                </div><!--article of child1 of major1-->
                <hr>
              </div><!--child1 of major1-->

        </div><!--article of major1-->
        <hr>
      </div><!--major1-->
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
