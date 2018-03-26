# linear-gradient

몇개의 색상들이 선형으로 배치되는 선형 그라디언트

- 양수의 경우, 0도 부터 시계방향으로 적용된다! 음수는 반대.
- 기본 값 : [to bottom]

~~~~
<linear-gradient> = linear-gradient(
	[ [ <angle> | to <side-or-corner> ] ,]?
	<color-stop>[, <color-stop>]+
)

<side-or-corner> = [left | right] || [top | bottom]
~~~~



## 1. 파라미터

### 1) **<**angle**>**

각도|키워드|방향
-----|----|--------
0deg|to top|위쪽 방향
90deg|to right|오른쪽 방향
180deg|to bottom|**아래쪽 방향**
270deg|to left|왼쪽 방향
45deg|to top right|오른쪽 위 방향
225deg|to bottom left|왼쪽 아래 방향


#### 예시
하늘색에서 파란색으로 그라디언트

- 0deg (to top)

<div style="height:100px; background:linear-gradient(0deg, aqua, darkblue);"></div>

- 90deg (to right)

<div style="height:100px; background:linear-gradient(90deg, aqua, darkblue);"></div>

- 180deg (to bottom) : 기본값

<div style="height:100px; background:linear-gradient(180deg, aqua, darkblue);"></div>

<div style="height:100px; background:linear-gradient(aqua, darkblue);"></div>

- 270deg (to left)

<div style="height:100px; background:linear-gradient(270deg, aqua, darkblue);"></div>

- 45deg (to top right)

<div style="width:300px; height:300px; background:linear-gradient(45deg, aqua, darkblue);"></div>

- 225deg (to bottom left)

<div style="width:300px; height:300px; background:linear-gradient(225deg, aqua, darkblue);"></div>



<br>

### 2) **<**color-stop**>**

- linear-gradient(red, blue);

<div style="width:300px; height:300px; background:linear-gradient(red, blue);"></div>

- linear-gradient(red 50%, blue 50%);

<div style="width:300px; height:300px; background:linear-gradient(red 50%, blue 50%);"></div>

- linear-gradient(red 80%, blue);

<div style="width:300px; height:300px; background:linear-gradient(red 80%, blue);"></div>

- linear-gradient(red 80px, blue 150px, black 230px);

<div style="position:relative; width:300px; height:300px;"><div style="height:300px; background:linear-gradient(red 80px, blue 150px, black 230px);"></div><div style="position:absolute; top:80px; left:0; right:0; height:1px; background:yellow;"></div><div style="position:absolute; top:150px; left:0; right:0; height:1px; background:yellow;"></div><div style="position:absolute; top:230px; left:0; right:0; height:1px; background:yellow;"></div></div>



<br>


## 2. 활용 방법

repeat 상태에서 color, position, angle, size의 조합으로 여러가지 패턴을 만들 수 있다.

<div style="position:relative;"><div style="height:200px; background-image:linear-gradient(to right, #aaa 50%, #000 0); background-size:100px auto;"></div><div style="position:absolute; top:0; width:100px; height:200px; outline:2px solid red;"></div></div>

<div style="position:relative;"><div style="height:200px; background-image:linear-gradient(to right, #aaa 33.3%, #fff 0, #fff 66.6%, #000 0); background-size:100px auto;"></div><div style="position:absolute; top:0; width:100px; height:200px; outline:2px solid red;"></div></div>

<div style="position:relative;"><div style="height:200px; background-image:linear-gradient(#aaa 10%, #000 0); background-size:auto 10px;"></div><div style="position:absolute; top:0; left:0; right:0; height:10px; outline:2px solid red;"></div></div>

<div style="position:relative;"><div style="height:200px; background-image:linear-gradient(to top right, #aaa 50%, #000 0); background-size:100px 100px;"></div><div style="position:absolute; top:0; width:100px; height:100px; outline:2px solid red;"></div></div>

<div style="position:relative;"><div style="height:200px; background-image:linear-gradient(to top right, black 25%, #aaa 0, #aaa 50%, black 0, black 75%, #aaa 0); background-size:100px 100px;"></div><div style="position:absolute; top:0; width:100px; height:100px; outline:2px solid red;"></div></div>

<div style="position:relative;"><div style="height:200px; background:#000; background-image:linear-gradient(#aaa 2%, transparent 0), linear-gradient(to right, #aaa 2%, transparent 0); background-size:50px 50px;"></div><div style="position:absolute; top:0; width:50px; height:50px; outline:2px solid red;"></div></div>

<div style="position:relative;"><div style="height:200px; background-image:linear-gradient(rgba(0,0,0,.5) 50%, transparent 0), linear-gradient(to right, rgba(0,0,0,.5) 50%, transparent 0); background-size:50px 50px;"></div><div style="position:absolute; top:0; width:50px; height:50px; outline:2px solid red;"></div></div>


<br>


## 3. 프리픽스

~~~~
background: -moz-linear-gradient(90deg, #ffffff 0%, #f1f1f1 100%); /* ff3.6+ */

background: -webkit-gradient(linear, left top, left bottom, color-stop(0%, #f1f1f1), color-stop(100%, #ffffff)); /* safari4+,chrome */

background: -webkit-linear-gradient(90deg, #ffffff 0%, #f1f1f1 100%); /* safari5.1+,chrome10+ */

background: -o-linear-gradient(90deg, #ffffff 0%, #f1f1f1 100%); /* opera 11.10+ */

background: -ms-linear-gradient(90deg, #ffffff 0%, #f1f1f1 100%); /* ie10+ */

background: linear-gradient(0deg, #ffffff 0%, #f1f1f1 100%); /* w3c */

filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#f1f1f1', endColorstr='#ffffff',GradientType=0 ); /* ie6-9 */
~~~~



<br><br><br><br><br>



# radial-gradient

원형 그라디언트는 그라디언트의 center와 사이즈, 모양을 정의해야 한다.
기본값 : [circle at center] -> 색상값만 써도 됨

~~~~
<radial-gradient> = radial-gradient(

  [ [ circle               || <length> ]                          [ at <position> ]? , |

    [ ellipse              || [ <length> | <percentage> ]{2} ]    [ at <position> ]? , |

    [ [ circle | ellipse ] || <extent-keyword> ]                  [ at <position> ]? , |

    at <position> ,

  ]?

  <color-stop> [ , <color-stop> ]+
)

<extent-keyword> = closest-corner | closest-side | farthest-corner | farthest-side
~~~~



## 파라미터

### 1. **<**shape**>** 와 **<**length**>**
shape 키워드를 굳이 쓰지 않더라도, x축 길이 하나만 쓰면 정원, y축 길이까지 쓰면 타원으로 그려진다.

#### circle
그라디언트의 모양을 정원형으로 한다.

<div style="width:200px; height:200px; background:radial-gradient(100px at center, #fff, #000);"></div>



#### ellipse

- 그라디언트의 모양을 타원형으로 한다.
- 추가로 y축 방향의 길이를 쓸 수 있다.


![](https://developer.mozilla.org/files/3795/radial%20gradient.png)

<div style="width:200px; height:200px; background:radial-gradient(50px 150px at center, #fff, #000);"></div>



<br>



### 2. 추가적인 키워드

length 대신 키워드를 사용할 수 있다

#### closest-side

ending shape가 그라디언트의 중심에서 가장 가까운 그라디언트 박스 모서리를 만나게끔 그라디언트된다.

<div style="height:200px; background:radial-gradient(closest-side circle at center, black, red, yellow);"></div>

<div style="height:200px; background:radial-gradient(closest-side ellipse at 100px 50px, black, red, yellow);"></div>



#### farthest-side

ending shape가 그라디언트의 중심에서 가장 먼 그라디언트 박스 모서리를 만나게끔 그라디언트된다.

<div style="height:200px; background:radial-gradient(farthest-side circle at center, black, red, yellow);"></div>

<div style="height:200px; background:radial-gradient(farthest-side ellipse at 100px 50px, black, red, yellow);"></div>



#### closest-corner

ending shape가 그라디언트의 중심에서 가장 가까운 꼭지점을 지나가게끔 그라디언트된다.

<div style="height:200px; background:radial-gradient(closest-corner circle at 200px 30px, black, red, yellow);"></div>

<div style="height:200px; background:radial-gradient(closest-corner ellipse at 200px 30px, black, red, yellow);"></div>



#### farthest-corner

ending shape가 그라디언트의 중심에서 가장 먼 꼭지점을 지나가게끔 그라디언트된다.

<div style="height:100px; background:radial-gradient(farthest-corner circle at 200px 30px, black, red, yellow);"></div>

<div style="height:100px; background:radial-gradient(farthest-corner ellipse at 200px 30px, black, red, yellow);"></div>



<br>

### 3. **<**position**>**

- (0, 0)

<div style="height:200px; background:radial-gradient(100px circle at 0 0, white, black);"></div>

- (0, 100%)

<div style="height:200px; background:radial-gradient(100px circle at 0 100%, white, black);"></div>

- (100%, 0)

<div style="height:200px; background:radial-gradient(100px circle at 100% 0, white, black);"></div>

- (100%, 100%)

<div style="height:200px; background:radial-gradient(100px circle at 100% 100%, white, black);"></div>



<br>



### 4. **<**color-stop**>**

- radial-gradient(red, blue);

<div style="width:200px; height:200px; background:radial-gradient(red, blue);"></div>

- radial-gradient(red 50%, blue 50%);

<div style="width:200px; height:200px; background:radial-gradient(red 50%, blue 50%);"></div>

- radial-gradient(red 80%, blue);

<div style="width:200px; height:200px; background:radial-gradient(red 80%, blue);"></div>

- radial-gradient(red 40px, blue 100px, black 160px);

<div style="position:relative; width:300px; height:300px;"><div style="height:300px; background:radial-gradient(red 40px, blue 100px, black 160px);"></div><div style="position:absolute; top:50%; left:50%; margin:-160px 0 0 -160px; width:320px; height:320px; border:1px solid yellow; border-radius:50%;"></div><div style="position:absolute; top:50%; left:50%; margin:-100px 0 0 -100px; width:200px; height:200px; border:1px solid yellow; border-radius:50%;"></div><div style="position:absolute; top:50%; left:50%; margin:-40px 0 0 -40px; width:80px; height:80px; border:1px solid yellow; border-radius:50%;"></div></div>

<br>



## 활용 방법

repeat 상태에서 color, position, size, shape의 조합으로 여러가지 패턴을 만들 수 있다.

<div style="position:relative;"><div style="height:200px; background:#000; background-image:radial-gradient(#fff 30%, transparent 0); background-size:100px 100px;"></div><div style="position:absolute; top:0; width:100px; height:100px; outline:2px solid red;"></div></div>

<div style="position:relative;"><div style="height:200px; background:#000; background-image:radial-gradient(#eee 30%, transparent 0), radial-gradient(#eee 30%, transparent 0); background-size:50px 50px; background-position:0 0, 25px 25px;"></div><div style="position:absolute; top:0; width:50px; height:50px; outline:2px solid red;"></div><div style="position:absolute; left:25px; top:25px; width:50px; height:50px; outline:2px solid red;"></div></div>



<br><br><br><br><br>



# repeating-linear-gradient

파라미터 등은 linear-gradient와 같으나, 아래 코드와 같이 color-stop들이 무한히 반복된다.

~~~~

linear-gradient(..., red -30px, blue 10px, red 10px, blue 50px, red 50px, blue 90px, ...)

repeating-linear-gradient(red 10px, blue 50px)

~~~~



> 비교

<div style="height:100px; background:linear-gradient(to right, red 10px, blue 50px);"></div>

<div style="height:100px; background:repeating-linear-gradient(to right, red 10px, blue 50px);"></div>



<br><br><br><br><br>



# repeating-radial-gradient

파라미터 등은 radial-gradient와 같으나, 아래 코드와 같이 color-stop들이 무한히 반복된다.

~~~~

radial-gradient(..., red -30px, blue 10px, red 10px, blue 50px, red 50px, blue 90px, ...)

repeating-radial-gradient(red 10px, blue 50px)

~~~~



> 비교
<div style="width:200px; height:200px; background:radial-gradient(red 10px, blue 50px);"></div>
<div style="width:200px; height:200px; background:repeating-radial-gradient(red 10px, blue 50px);"></div>
