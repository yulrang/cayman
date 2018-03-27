# flex

![](https://www.w3.org/TR/css-flexbox-1/images/flex-direction-terms.svg)

- main-axis : 플렉스 아이템들이 놓여지는 주축
- cross-axis : main-axis에 수직인 축
- main-start, main-end : 플렉스 아이템이 놓여지는 시작과 끝
- cross-start, cross-end :

<br>

## 1. flex container
`display` 속성을 사용하여 블럭 레벨, 인라인 레벨의 플렉스 컨테이너 박스를 만들 수 있다.

~~~~
display:flex;
display:inline-flex;
~~~~

> flex vs inline-flex

<iframe height='242' scrolling='no' title='LxgWmZ' src='//codepen.io/yulrang/embed/LxgWmZ/?height=242&theme-id=0&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/yulrang/pen/LxgWmZ/'>LxgWmZ</a> by yura (<a href='http://codepen.io/yulrang'>@yulrang</a>) on <a href='http://codepen.io'>CodePen</a>.

</iframe>



<br>



### 1) flex formatting context
플렉스 컨테이너는 내용에 블럭 레이아웃 대신 플렉스 레이아웃을 사용하는 새로운 플렉스 포맷팅 컨텍스트를 설정한다.
특히, 다음과 같은 영향을 끼친다.

- `column-*`, `:first-line`, `:first-letter` 속성은 플렉스 컨테이너에 적용되지 않는다.
- `float`, `clear`, `vertical-align`는 플렉스 컨테이너 안에서 영향을 끼치지 못한다.
- 플렉스 컨테이너의 마진은 그것의 내용의 마진과 병합되지 않는다.

<br><br><br>


## 2. flex items
플렉스 컨테이너 안의 흐름이 있는 박스들
플렉스 컨테이너의 바로 안에 속해 있는 연속된 흐름의 텍스트 각각은 익명 플렉스 아이템 안에 감싸진다.
그러나, 공백만을 포함하는 익명 플렉스 아이템은 렌더링되지 않는다.

플렉스 아이템은 내용을 위해 새로운 포맷팅 컨텍스트를 수립한다.

포맷팅 컨텍스트의 타입은 보통 `display` 값에 따라 결정되지만, **플렉스 아이템은 플렉스 컨테이너 안에서 스스로 블럭 레벨이 아닌 플렉스 레벨 박스가 된다.**

<iframe height='292' scrolling='no' title='rjqyVP' src='//codepen.io/yulrang/embed/rjqyVP/?height=292&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/yulrang/pen/rjqyVP/'>rjqyVP</a> by yura (<a href='http://codepen.io/yulrang'>@yulrang</a>) on <a href='http://codepen.io'>CodePen</a>.

</iframe>

<br>



### 1) 플렉스 아이템의 절대 배치
플렉스 컨테이너 안의 절대 배치된 자식들은 플렉스 레이아웃에 포함되지 않는다.

<iframe height='265' scrolling='no' title='ygRbdV' src='//codepen.io/yulrang/embed/ygRbdV/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/yulrang/pen/ygRbdV/'>ygRbdV</a> by yura (<a href='http://codepen.io/yulrang'>@yulrang</a>) on <a href='http://codepen.io'>CodePen</a>.

</iframe>

<br>

### 2) 플렉스 아이템의 margin과 padding
인접한 플렉스 아이템들의 마진은 병합되지 않는다.

<div class="wrap" style="display:flex; flex-direction:column; width:300px; height:200px; background:#eee;"><div class="box" style="width:50px; height:50px; margin-top:5%; background:red;"></div><div class="box" style="width:50px; height:50px; margin-top:5%; background:red;"></div></div>


<br>

<div class="alert alert-danger">마진과 패딩의 %값은 브라우저마다 다른 방법으로 해석된다.

- 그들의 고유 축에 대하여 해석한다. left/right 퍼센트는 width에 대한, top/bottom은 height에 대한 비율로 지정
- 포함된 축에 대하여 해석한다. 모든 방향의 퍼센트가 width에 대한 비율로 지정</div>


<br>

### 3) 플렉스 아이템의 z-order
플렉스 아이템들은 인라인 블럭 박스와 똑같은 방법으로 그려진다.
단, `order` 속성에 따라 마크업 순서 변경이 이루어질 수 있고, `auto` 값이 아닌 `z-index` 값은 `position:static` 이더라도, stacking context를 만든다.

<iframe height='265' scrolling='no' title='flex item z-order' src='//codepen.io/yuuuuul/embed/wrXKZm/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/yuuuuul/pen/wrXKZm/'>flex item z-order</a> by yuuuuul (<a href='https://codepen.io/yuuuuul'>@yuuuuul</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

<br>

### 4) 플렉스 아이템의 collapse
플렉스 아이템에 `visibility:collapse`이 적용될 경우, collapsed flex item이 된다. table-row나 table-column 요소에 `visibility:collapse`가 적용된 것과 비슷한 효과를 낸다.
collapsed flex item은 전체 렌더링에서 제거되지만, 플렉스 라인의 cross-size를 안정적으로 하게 하기 위해 strut 뒤에 남아있다.

만약, 플렉스 컨테이너가 오직 하나의 플렉스 라인을 가진다면, 동적으로 collapsing 혹은 uncollapsing된 아이템들은 컨테이너의 main size에 영향을 미치지만, 컨테이너의의 cross size와 나머지 페이지 레이아웃에는 영향을 미치지 않는다.

flex line 래핑은 collapsing 이후에 다시 행해지지만, 여러개 라인 플렉스 컨테이너의 cross-size는 바뀌지 않을 것이다.

<iframe height='265' scrolling='no' title='flex item collapse' src='//codepen.io/yuuuuul/embed/boKEWQ/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/yuuuuul/pen/boKEWQ/'>flex item collapse</a> by yuuuuul (<a href='https://codepen.io/yuuuuul'>@yuuuuul</a>) on <a href='https://codepen.io'>CodePen</a>.

</iframe>


<br><br><br>


## 3. Flex Lines
플렉스 컨테이너 안의 플렉스 아이템들은 플렉스 라인대로 정렬되어 놓여진다. 레이아웃 알고리즘을 통해 가상 컨테이너가 그룹화와 정렬을 한다.
플렉스 컨테이너는 `flex-wrap` 속성에 의해 싱글라인이나 멀티라인이 될 수 있다.

- 싱글 라인 플렉스 컨테이너 : 자식 요소들이 컨테이너 밖으로 넘치더라도 모든 자식을 싱글라인 안에 놓는다.
- 멀티 라인 플렉스 컨테이너 : 자식 요소들이 컨테이너 밖으로 넘치면, 새로운 라인에 놓여지도록 한다.

<br><br><br>


## 4. ordering과 orientation
플렉스 컨테이너의 내용은 `flex-direction`, `flex-wrap`, `order` 속성을 통해 어떤 방향이나 순서로 놓여질 수 있다.

<div class="alert alert-danger">플렉스 레이아웃의 순서 재배치 기능은 오직 시각적 렌더링에만 영향을 미친다. 스크린 리더의 스피치 리딩 순서는 마크업 순서에 따른다.

`order` 속성이나, `flex-flow`, `flex-direction`의 `*-reverse` 값은 올바른 마크업 순서를 지킨 후 사용해야 접근성에 위배되지 않는다.</div>


<br>

### 1) flex-direction : 플렉스의 플로우 방향
플렉스 컨테이너의 주축(main-axis)의 방향을 설정함으로써 플렉스 아이템들이 플렉스 컨테이너 안에서 어떻게 놓여질 것인지 정의한다.


항목|내용
----|-------
적용 대상|플렉스 컨테이너
초기값|row
값|row, row-reverse, column, column-reverse
상속|X



#### (1) row
플렉스 컨테이너의 main-axis가 현재 writing-mode의 인라인 축과 동일한 방향을 가진다.
main-start와 main-end의 방향이 현재 writing mode의 inline-start와 inline-end 방향과 상대적으로 일치한다.

#### (2) row-reverse
플렉스 컨테이너의 main-axis가 현재 writing-mode의 인라인 축과 동일한 방향을 가진다.
main-start와 main-end의 방향이 현재 writing mode의 inline-start와 inline-end 방향과 반대된다.

#### (3) column
플렉스 컨테이너의 main-axis가 현재 writing-mode의 블럭 축과 동일한 방향을 가진다.
main-start와 main-end의 방향이 현재 writing mode의 block-start와 block-end 방향과 상대적으로 일치한다.

#### (4) column-reverse
플렉스 컨테이너의 main-axis가 현재 writing-mode의 블럭 축과 동일한 방향을 가진다.
main-start와 main-end의 방향이 현재 writing mode의 block-start와 block-end 방향과 반대된다.

<iframe height='265' scrolling='no' title='mBKrwX' src='//codepen.io/yuuuuul/embed/mBKrwX/?height=265&theme-id=0&default-tab=html,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/yuuuuul/pen/mBKrwX/'>mBKrwX</a> by yuuuuul (<a href='https://codepen.io/yuuuuul'>@yuuuuul</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

<br>

### 2) flex-wrap : 플렉스 라인 래핑
플렉스 컨테이너가 싱글 라인인지 멀티 라인인지 여부와 cross-axis의 방향을 제어하며, 새로운 라인이 어떤 방향으로 쌓이게 할 지를 결정한다.

항목|내용
----|-------
적용 대상|플렉스 컨테이너
초기값|nowrap
값|nowrap, wrap, wrap-reverse
상속|X

#### (1) nowrap
플렉스 컨테이너가 싱글라인이 되도록 한다.
cross-start 방향은 현재 writing mode의 inline-start나 block-start 방향과 일치하며, cross-end 방향은 cross-start 방향과 반대된다.

#### (2) wrap
플렉스 컨테이너가 멀티라인이 되도록 한다.
cross-start 방향은 현재 writing mode의 inline-start나 block-start 방향과 일치하며, cross-end 방향은 cross-start 방향과 반대된다.

#### (3) wrap-reverse
플렉스 컨테이너가 멀티라인이 되도록 한다.
cross-start와 cross-end 방향이 서로 바뀐다.

<iframe height='265' scrolling='no' title='flex-wrap' src='//codepen.io/yuuuuul/embed/MEXJbG/?height=265&theme-id=0&default-tab=html,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/yuuuuul/pen/MEXJbG/'>flex-wrap</a> by yuuuuul (<a href='https://codepen.io/yuuuuul'>@yuuuuul</a>) on <a href='https://codepen.io'>CodePen</a>.

</iframe>


<br>


### 3) flex-flow : flex-direction 과 flex-wrap의 단축 속성
플렉스 컨테이너의 main-axis와 cross-axis를 함께 정의할 수 있는 `flex-direction`과 `flex-wrap`의 단축 속성이다.

항목|내용
----|-------
적용 대상|플렉스 컨테이너
초기값|row nowrap
값|\<flex-drection\> ∥ \<flex-wrap\>;
상속|X


<div class="alert alert-info">main-axis와 cross-axis의 방향을 결정 할 때는 writing mode가 어떻게 설정되어 있는지 확인해야 한다.

- horizontal-tb 인 경우 : 영어, 한글 등
- vertical-rl 인 경우 : 일어 등</div>


<br>

### 4) order : 순서 디스플레이
플렉스 아이템은 기본적으로 마크업과 동일한 순서로 놓여지지만, `order` 속성을 이용해 순서를 바꿀 수 있다.
플렉스 아이템에 정수 값을 할당하여 순서 그룹을 지정할 수 있다.
플렉스 컨테이너는 `order`값에 따라 순서가 수정된 마크업 순서대로 플렉스 아이템들을 놓는다.
순서는 작은 숫자부터 차례대로 시작되며, 숫자가 같을 경우, 마크업 순서대로 놓이게 된다.


항목|내용
----|-------
적용 대상|플렉스 아이템, 플렉스 컨테이너의 절대 배치된 자식들
초기값|0
값|정수
상속|X


<br><br><br>


## 5. Flexibility
### 1) flex : 단축 속성
`flex-grow`, `flex-shrink`, `flex-basis`의 단축 속성이다. 박스가 플렉스 아이템이 아닌 경우 영향을 미치지 못한다.


항목|내용
----|-------
적용 대상|플렉스 아이템
초기값|1 0 auto
값|none ｜&lt;flex-grow&gt; &lt;flex-shrink&gt; ∥ &lt;flex-basis&gt;
상속|X

<br>

### 2) flex-grow
숫자를 통해 flex grow 요인을 설정한다. 음수는 불가능하고, 생략될 경우, 1로 설정됨.
플렉스 컨테이너 안의 나머지 플렉스 아이템들에 상대적으로 얼마만큼 공간을 차지할 것인지 결정.

항목|내용
----|-------
적용 대상|플렉스 아이템
초기값|0
값|숫자
상속|X

<iframe height='265' scrolling='no' title='[CSS] flex-grow' src='//codepen.io/2yulrang/embed/jYwOxM/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/2yulrang/pen/jYwOxM/'>[CSS] flex-grow</a> by leeYura (<a href='https://codepen.io/2yulrang'>@2yulrang</a>) on <a href='https://codepen.io'>CodePen</a>.

</iframe>



<br>

### 3) flex-shrink
숫자를 통해 flex shrink 요인을 설정한다. 음수는 불가능하다.
~~~~
flex item의 너비 = flex-basis 값 - negative space * flex-shrink 비율
~~~~

항목|내용
----|-------
적용 대상|플렉스 아이템
초기값|1
값|숫자
상속|X

<iframe height='265' scrolling='no' title='[CSS] flex-grow & flex-shrink' src='//codepen.io/2yulrang/embed/LeLPXj/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/2yulrang/pen/LeLPXj/'>[CSS] flex-grow & flex-shrink</a> by leeYura (<a href='https://codepen.io/2yulrang'>@2yulrang</a>) on <a href='https://codepen.io'>CodePen</a>.

</iframe>

<br>

### 4) flex-basis
플렉스아이템의 main size 초기값을 설정한다.

항목|내용
----|-------
적용 대상|플렉스 아이템
초기값|auto
값|content ｜&lt;width&gt;
상속|X

<br><br><br>



## 6. 플렉스 아이템의 정렬
### 1) auto margins

<br>



### 2) justify-content : axis 정렬

<iframe height='265' scrolling='no' title='justify-content' src='//codepen.io/yuuuuul/embed/pWZvEq/?height=265&theme-id=0&default-tab=html,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/yuuuuul/pen/pWZvEq/'>justify-content</a> by yuuuuul (<a href='https://codepen.io/yuuuuul'>@yuuuuul</a>) on <a href='https://codepen.io'>CodePen</a>.

</iframe>



<br>



### 3) align-items : cross-axis 정렬



<br>



### 4) align-self : cross-axis 정렬



<br>



### 5) align-content : 플렉스 라인 감싸기



<br>



### 6) 플렉스 컨테이너 베이스라인



<br><br><br>
