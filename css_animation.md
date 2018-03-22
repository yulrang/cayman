---
layout: default
---

# [CSS] animation
어느 시간 동안의 CSS 속성 변화를 키프레임의 집합으로써 정의할 수 있다.

transition과 비슷하나, **속성 값의 변화를 명시적으로 하는데** 에 차이점이 있다. 애니메이션은 키프레임을 사용한 명시적 값을 필요로 한다.

반복 횟수, 시작과 끝 값의 대체가 있을 것인지, 정지여부, 시작 시간의 딜레이 등 애니메이션의 많은 부분을 조정할 수 있다.

<br>

## 1. 특징
1. 한 시간 지점에 똑같은 속성에 대해 여러 애니메이션이 적용된 경우, 마지막으로 선언된 애니메이션의 것이 적용된다.
<iframe height='265' scrolling='no' title='animation multiple' src='//codepen.io/2yulrang/embed/YQRgqB/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/2yulrang/pen/YQRgqB/'>animation multiple</a> by leeYura (<a href='https://codepen.io/2yulrang'>@2yulrang</a>) on <a href='https://codepen.io'>CodePen</a></iframe>

2. 애니메이션은 애니메이션 적용 전, 딜레이 시간 만료 전, 적용 후의 계산값에 영향을 미치지 않는다.

3. 애니메이션은 문서가 로딩되는 순간 시작된다.
스타일을 수정하여 지정한 애니메이션은 스타일시트가 해석될 때 시작됨. (`:hover`, 스크립트 제어 등)

4. 애니메이션을 다시 시작하려면 애니메이션을 제거한 다음 다시 적용해야 함.

<iframe height='265' scrolling='no' title='animation restart' src='//codepen.io/2yulrang/embed/vZQMwZ/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/2yulrang/pen/vZQMwZ/'>animation restart</a> by leeYura (<a href='https://codepen.io/2yulrang'>@2yulrang</a>) on <a href='https://codepen.io'>CodePen</a>.</iframe>

5. 애니메이션을 변경하려면 `animation-name` 값을 변경해야함.
해당 속성을 이용하여 애니메이션을 삭제하는 경우 적용된 다른 애니메이션은 계속됨.

<iframe height='265' scrolling='no' title='animation interaction' src='//codepen.io/2yulrang/embed/LLXvzV/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/2yulrang/pen/LLXvzV/'>animation interaction</a> by leeYura (<a href='https://codepen.io/2yulrang'>@2yulrang</a>) on <a href='https://codepen.io'>CodePen</a>.</iframe>

6. `display:none`이 설정되면 애니메이션이 모두 종료되고, 해제되면 다시 시작됨.
<iframe height='265' scrolling='no' title='jwQJja' src='//codepen.io/2yulrang/embed/jwQJja/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/2yulrang/pen/jwQJja/'>jwQJja</a> by leeYura (<a href='https://codepen.io/2yulrang'>@2yulrang</a>) on <a href='https://codepen.io'>CodePen</a>.</iframe>

<br>

## 2. keyframe
키프레임은 애니메이션이 진행되는 동안 여러 지점의 애니메이팅되는 속성값을 정의하기 위해 사용된다.
`animation-name` 속성으로 애니메이션을 참조할 수 있다.

- 키프레임은 우선순위 규칙이 적용되지 않는다.
- 빈 키프레임을 사용해서 같은 이름의 키프레임을 숨길 수 있다. (??)

<iframe height='265' scrolling='no' title='keyframe cascade' src='//codepen.io/2yulrang/embed/awPpQa/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/2yulrang/pen/awPpQa/'>keyframe cascade</a> by leeYura (<a href='https://codepen.io/2yulrang'>@2yulrang</a>) on <a href='https://codepen.io'>CodePen</a>.</iframe>


### 1) keyframe 선택자
퍼센트 값이나 `from`, `to`와 같은 키워드로 구성되어 있다.
**0은 잘못된 키 프레임 선택자** 이며, 음수 백분율이나 100%보다 큰 값은 무시된다.

~~~~
from == 0%
to == 100%
~~~~


### 2) keyframe 선언 블록
속성과 값으로 구성되어 있다.

- 애니메이팅 될 수 없는 속성들은 무시된다.
- `!important`로 규정된 선언은 무시된다.

### 3) 키프레임에서의 timing function 사용
다음 키프레임으로 이동할 때 `animation-timing-function`을 사용할 수 있다.
단, `to`나, `100%` 키프레임 선택자에 적용된 timing function은 무시된다.

<iframe height='349' scrolling='no' title='timing functions for keyframes' src='//codepen.io/2yulrang/embed/dRLegr/?height=349&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/2yulrang/pen/dRLegr/'>timing functions for keyframes</a> by leeYura (<a href='https://codepen.io/2yulrang'>@2yulrang</a>) on <a href='https://codepen.io'>CodePen</a>.</iframe>


<br><br>

# animation-name
적용될 애니메이션의 리스트를 정의한다. 각 이름은 키프레임을 참조하는데 쓰인다.

- 매치되는 이름이 없을 경우, 애니메이션이 실행되지 않는다.
- `none`인 경우, 애니메이션이 없어진다. 오버라이드하여 사용할 수 있다.
- 똑같은 속성에 대해 여러 애니메이션이 적용된 경우, 가장 마지막에 선언된 것이 우선한다.


> **※ 리스트매칭**
> 애니메이션 이름 리스트는 반드시 상응하는 애니메이션 속성 리스트가 아래에 있어야 한다.
만약 목록의 길이가 같은 길이가 아니라면, 애니메이션 이름 리스트의 길이에 따른 리스트매칭이 이루어진다.
> `background-image`나 `transition` 리스트매칭과 유사하다.

<iframe height='265' scrolling='no' title='animation property list-match' src='//codepen.io/2yulrang/embed/awxKLr/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/2yulrang/pen/awxKLr/'>animation property list-match</a> by leeYura (<a href='https://codepen.io/2yulrang'>@2yulrang</a>) on <a href='https://codepen.io'>CodePen</a>.</iframe>


<br><br>


# animation-duration
애니메이션의 한 사이클이 종료될 때 까지 걸리는 시간의 길이를 정의한다.

- 초기값 : 0s
- `animation-fill-mode`



<br><br>

# animation-timing-function
애니메이션의 한 사이클이 어떻게 진행될 것인지 정의한다. `transition-timing-function` 속성과 비슷하다.
키프레임 에니메이션에서 해당 속성은 애니메이션 전체에 걸쳐서가 아니라 키프레임 간에 적용된다.

- 초기값 : `ease`



[참고 - transition-timing-function](http://sanissan.tistory.com/entry/CSS-Transition#transition-timing-function)



<iframe height='352' scrolling='no' title='ease-in-out' src='//codepen.io/2yulrang/embed/vJYmmr/?height=352&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/2yulrang/pen/vJYmmr/'>ease-in-out</a> by leeYura (<a href='https://codepen.io/2yulrang'>@2yulrang</a>) on <a href='https://codepen.io'>CodePen</a>.</iframe>



<br>



<iframe height='352' scrolling='no' title='ease-in & ease-out' src='//codepen.io/2yulrang/embed/gxORKP/?height=352&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/2yulrang/pen/gxORKP/'>ease-in & ease-out</a> by leeYura (<a href='https://codepen.io/2yulrang'>@2yulrang</a>) on <a href='https://codepen.io'>CodePen</a>.</iframe>



<br><br>

# animation-iteration-count
애니메이션 사이클이 플레이되는 횟수를 정의한다.
음수는 허용되지 않으며, 정수가 아닌 수를 입력하면 값에 따라 애니메이션이 도중에 멈추게 된다.
해당 속성은 `animation-direction`의 `alternate`값과 결합하여 애니메이션 사이클을 번갈아 실행할 때 사용할 수 있다.

<br><br>

# animation-direction
애니메이션이 일부 혹은 전체 사이클에서 역으로 재생되게 할 것인지 정의할 수 있다.
애니메이션이 역으로 재생될 경우, timing function도 역으로 된다. ( ease-in  >  ease-out )


## 1. 값

### 1) normal
애니메이션의 모든 반복이 재생됨

### 2) reverse
애니메이션의 모든 반복이 정의된 방법의 역방향으로 재생됨

### 3) alternate
애니메이션의 홀수번째 반복은 정방향으로, 짝수번째 반복은 역방향으로 재생됨

### 4) alternate-reverse
애니메이션의 홀수번째 반복은 역방향으로, 짝수번째 반복은 정방향으로 재생됨



<iframe height='265' scrolling='no' title='animation-direction' src='//codepen.io/2yulrang/embed/xLbNbw/?height=265&theme-id=0&default-tab=html,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/2yulrang/pen/xLbNbw/'>animation-direction</a> by leeYura (<a href='https://codepen.io/2yulrang'>@2yulrang</a>) on <a href='https://codepen.io'>CodePen</a>.</iframe>



<br><br>


# animation-play-state
애니메이션의 실행/정지 여부를 정의한다. 해당 속성의 값을 `paused`로 지정하여 실행중인 애니메이션을 정지시킬 수 있고, `running`로 지정하여 정지되어 있는 애니메이션을 실행시킬 수 있다.

정지된 애니메이션이 다시 실행될 경우, 정적인 상태에서의 값을 계속해서 이어 보여준다.


<iframe height='265' scrolling='no' title='animation-play-state' src='//codepen.io/2yulrang/embed/aydMBd/?height=265&theme-id=0&default-tab=js,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/2yulrang/pen/aydMBd/'>animation-play-state</a> by leeYura (<a href='https://codepen.io/2yulrang'>@2yulrang</a>) on <a href='https://codepen.io'>CodePen</a>.</iframe>



<br><br>


# animation-delay
애니메이션이 적용된 후 실행이 시작되는 지점을 정의할 수 있다. `0s` 값은 애니메이션이 적용되자마자 실행될 것임을 의미한다.

음의 값이 적용된 경우, 적용된 순간에 바로 실행되는 것 처럼 보이지만, 지정된 값에서 부분적으로 시작한다.



<iframe height='265' scrolling='no' title='animation-delay' src='//codepen.io/2yulrang/embed/Yxwmzv/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/2yulrang/pen/Yxwmzv/'>animation-delay</a> by leeYura (<a href='https://codepen.io/2yulrang'>@2yulrang</a>) on <a href='https://codepen.io'>CodePen</a>.</iframe>

<br><br>







# animation-fill-mode
애니메이션의 실행시간 **이외의 시간에** 어떤 속성 값을 적용시킬 것인지 정의한다.



## 1. 값

### 1) none
초기값. 요소의 속성값에 영향을 미치지 않음

### 2) backwards
애니메이션이 딜레이되는 시간 동안에 애니메이션의 한 사이클을 시작할 때 정의한 속성 값이 적용됨

- animation-direction이 `normal`이나 `alternate`일 경우에는 from 키프레임의 값이 적용됨
- animation-direction이 `reverse`이나 `alternate-reverse`일 경우에는 to 키프레임의 값이 적용됨


<iframe height='265' scrolling='no' title='animation-fill-mode - 1. delay' src='//codepen.io/2yulrang/embed/EvypEx/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/2yulrang/pen/EvypEx/'>animation-fill-mode - 1. delay</a> by leeYura (<a href='https://codepen.io/2yulrang'>@2yulrang</a>) on <a href='https://codepen.io'>CodePen</a>.</iframe>





### 3) forwards
애니메이션이 종료된 후, 애니메이션의 한 사이클을 종료할 때 정의한 속성 값이 적용됨

- animation-iteration-count가 0일 때, 한 사이클이 완료될 시점에 from 키프레임의 값이 적용됨.
- animation-iteration-count가 0보다 큰 정수일 때, 한 사이클이 완료될 시점에 to 키프레임의 값이 적용됨.

<iframe height='265' scrolling='no' title='animation-fill-mode - 2. forwards' src='//codepen.io/2yulrang/embed/Vzjgvq/?height=265&theme-id=0&default-tab=js,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/2yulrang/pen/Vzjgvq/'>animation-fill-mode - 2. forwards</a> by leeYura (<a href='https://codepen.io/2yulrang'>@2yulrang</a>) on <a href='https://codepen.io'>CodePen</a>.</iframe>



### 4) both
`forwards`와 `backwards`의 규칙을 모두 따름
