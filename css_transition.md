---
layout: default
---

# [CSS] transition
일반적으로 CSS 속성 값이 바뀔 때, 즉각적으로 바뀌어 렌더링되지만, transition 속성을 사용하여 새로운 CSS 속성 값으로의 전환을 구체적으로 정의할 수 있다.

`transition-property`, `transition-duration`, `transition-delay`, `transition-timing-function`의 단축 속성이다.

- 애니메이션이 가능한 CSS 속성들만 트랜지션 가능 [애니메이션이 가능한 속성 목록](https://www.w3.org/TR/css3-transitions/#properties-from-css-)
- 여러개의 트랜지션은 콤마로 분리하여 리스트로 작성
- 리스트 매칭 : 트랜지션 리스트들이 같은 길이가 아닌 경우, `transition-property` 리스트의 길이에 따라 각 속성 트랜지션이 시작되는 지점이 결정됨

<iframe height='265' scrolling='no' title='transition-property' src='//codepen.io/2yulrang/embed/awNQbG/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/2yulrang/pen/awNQbG/'>transition-property</a> by leeYura (<a href='https://codepen.io/2yulrang'>@2yulrang</a>) on <a href='https://codepen.io'>CodePen</a>.

</iframe>

<br>

> ※ Intermediate value (중간값)
> ![](https://www.w3.org/TR/css3-transitions/transition1.png)



<br><br>

# transition-property

| 항목       | 내용                        |
|: -----------|:---------------------------|
| 적용 대상   | 가상 요소를 포함한 모든 요소 |
| 초기값     | all                         |
| 상속       | X                           |



## 1. 값
~~~~
none | <single-transition-property> [ ‘,’ <single-transition-property> ]*
~~~~

### all
애니메이션이 가능한 모든 하위 속성에 대한 전환

### \<single-transition-property\>
단일 속성에 대한 전환

리스트로 작성하여 복수 전환이 가능하나 트랜지션이 불가능한 속성이 정의되어 있을 경우 무시한다. 단, 무시되더라도 **리스트 매칭은 유지된다.**

<iframe height='265' scrolling='no' title='transition-property invalid' src='//codepen.io/2yulrang/embed/XgdyeB/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/2yulrang/pen/XgdyeB/'>transition-property invalid</a> by leeYura (<a href='https://codepen.io/2yulrang'>@2yulrang</a>) on <a href='https://codepen.io'>CodePen</a>.

</iframe>


<br><br>

# transition-duration

항목|내용
----|----
적용 대상|가상 요소를 포함한 모든 요소
초기값|0s
상속|X

새로운 값으로 전환하는데의 시간이 얼마나 걸리도록 할 것인지 정의함
0s는 즉각적인 전환을 의미하며, 음수는 불가능

<br><br>


# transition-timing-function
전환이 진행되는 동안의 속도를 변화시킬 수 있다. 계단함수이나 베지어 곡선로 정의될 수 있다.

- 계단 함수 : 연산의 범위가 동일한 크기의 간격으로 나눈 수에 의해 정의됨. 또한, 출력비율의 변화를 각 간격의 시작에 줄 것인지, 끝에 줄 것인지 정의함
- 베지어 곡선 : 조절점의 좌표를 지정하여 곡선을 통해 출력비율의 변화를 정의

[베지어 곡선 그리기](http://cubic-bezier.com)

a> P_1, P_2의 x, y좌표를 정의 -> x1, y1, x2, y2
> 각 좌표값은 0~1의 실수



## 1. 값

### 1. 베지어 곡선 값

#### ease
cubic-bezier(0.25, 0.1, 0.25, 1)와 동일

#### linear
cubic-bezier(0, 0, 1, 1)와 동일

#### ease-in
cubic-bezier(0.42, 0, 1, 1)와 동일

#### ease-out
cubic-bezier(0, 0, 0.58, 1)와 동일

#### ease-in-out
cubic-bezier(0.42, 0, 0.58, 1)와 동일

#### cubic-bezier()
조절점의 P_1과 P_2의 x, y좌표를 정의. (x1, y1, x2, y2)

~~~~
cubic-bezier(<number>, <number>, <number>, <number>)
~~~~

![](http://slides.iamvdo.me/w3cafe12/img/trTimingFn.png)

<iframe height='560' scrolling='no' title='transition timing function _ bezier curve' src='//codepen.io/2yulrang/embed/YQWVgJ/?height=560&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/2yulrang/pen/YQWVgJ/'>transition timing function _ bezier curve</a> by leeYura (<a href='https://codepen.io/2yulrang'>@2yulrang</a>) on <a href='https://codepen.io'>CodePen</a>.

</iframe>



### 2. 계단 함수값

#### step-start
steps(1, start)와 동일

#### step-end
steps(1, end)와 동일

#### steps()
첫번째 파라미터는 단계의 수를, 두번째 파라미터는 단계 내에서 값의 변화를 처음과 끝 중 어디에 줄 것인지를 의미
두번째 파라미터가 생략될 경우, end로 계산됨

~~~~
steps(<integer>[, [ start | end ] ]?)
~~~~

<iframe height='459' scrolling='no' title='transition timing function _ step function' src='//codepen.io/2yulrang/embed/PjzKNp/?height=459&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/2yulrang/pen/PjzKNp/'>transition timing function _ step function</a> by leeYura (<a href='https://codepen.io/2yulrang'>@2yulrang</a>) on <a href='https://codepen.io'>CodePen</a>.</iframe>


<br><br>

#transition-delay

항목|내용
----|----
적용 대상|가상 요소를 포함한 모든 요소
초기값|0s
상속|X

트랜지션이 언제 시작될 것인지 정의한다.
음수값이 선언될 경우, 트랜지션이 즉각적으로 이루어진다. 트랜지션을 부분적으로 사용하고 싶을 때 쓰일 수 있다.

<iframe height='264' scrolling='no' title='transition-delay_negative' src='//codepen.io/2yulrang/embed/NgragV/?height=264&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/2yulrang/pen/NgragV/'>transition-delay_negative</a> by leeYura (<a href='https://codepen.io/2yulrang'>@2yulrang</a>) on <a href='https://codepen.io'>CodePen</a>.

</iframe>



<br><br>
