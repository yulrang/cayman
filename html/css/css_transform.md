# transform

항목|내용
----|-----
적용대상|블럭레벨, 인라인블럭레벨, table-row, table-row,group, table-header-group, table-footer-group, table-cell, table-caption
상속|X
%|바운딩 박스

요소의 좌표계에 적용된다. transform function 목록을 포함한다.
최종 변형 값은 [행렬](https://www.w3.org/TR/css-transforms-1/#mathematical-description)로 변환되어 적용된다.



## 1. 2D transform function

### 1) matrix()
여섯 개 값의 행렬 형식으로 2D 변형을 지정
~~~~
matrix( <number> [, <number> ]{5,5} )
~~~~

### 2) translate()
X축 벡터, Y축 벡터 값만큼 2D 이동. Y축 벡터값이 없을 경우, Y축 벡터값은 **0으로 계산됨**
~~~~
translate( <translation-value> [, <translation-value> ]? )
~~~~

<iframe height='493' scrolling='no' title='translate' src='//codepen.io/yulrang/embed/egemzP/?height=493&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/yulrang/pen/egemzP/'>translate</a> by yura (<a href='http://codepen.io/yulrang'>@yulrang</a>) on <a href='http://codepen.io'>CodePen</a>.

</iframe>

### 3) translateX()
X축 방향으로 주어진 값만큼 이동
~~~~
translateX( <translation-value> )
~~~~

### 4) translateY()
Y축 방향으로 주어진 값만큼 이동
~~~~
translateY( <translation-value> )
~~~~

### 5) scale()
X축 벡터, Y축 벡터만큼 2D 크기 변형. Y축 벡터값이 없을 경우, Y축 벡터값은 **X축 벡터값과 같은 값으로 계산됨**.
~~~~
scale( <number> [, <number> ]? )
~~~~

<iframe height='473' scrolling='no' title='scale' src='//codepen.io/yulrang/embed/egVXNY/?height=473&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/yulrang/pen/egVXNY/'>scale</a> by yura (<a href='http://codepen.io/yulrang'>@yulrang</a>) on <a href='http://codepen.io'>CodePen</a>.

</iframe>

### 6) scaleX()
X축 방향으로 크기 변형. 즉, Y축 벡터값이 1인 2D 크기 변형
~~~~
scaleX( <number> )
~~~~

### 7) scaleY()
Y축 방향으로 크기 변형. 즉, X축 벡터값이 1인 2D 크기 변형
~~~~
scaleY( <number> )
~~~~

### 8) rotate()
`transform-origin`속성으로 정의된 원점에 대하여 2D 회전
~~~~
rotate( <angle> )
~~~~

<iframe height='364' scrolling='no' title='RKQONv' src='//codepen.io/yulrang/embed/RKQONv/?height=364&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/yulrang/pen/RKQONv/'>RKQONv</a> by yura (<a href='http://codepen.io/yulrang'>@yulrang</a>) on <a href='http://codepen.io'>CodePen</a>.

</iframe>

### 9) skew()
X축 각도값, Y축 각도값만큼 2D 기울임. Y축 각도값이 없을 경우, Y축 각도값은 0으로 취급
~~~~
skew( <angle> [, <angle> ]? )
~~~~

<iframe height='492' scrolling='no' title='LxQvjX' src='//codepen.io/yulrang/embed/LxQvjX/?height=492&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/yulrang/pen/LxQvjX/'>LxQvjX</a> by yura (<a href='http://codepen.io/yulrang'>@yulrang</a>) on <a href='http://codepen.io'>CodePen</a>.

</iframe>

### 10) skewX()
X축을 따라 2D 기울임.
~~~~
skewX( <angle> )
~~~~

### 11) skewY()
Y축을 따라 2D 기울임.
~~~~
skewY( <angle> )
~~~~

<br>

## 2. 3D transform function

### 1) matrix3d()
4*4 동차행렬에 의해 정의된 3d 변형
~~~~
matrix3d( <number> [, <number> ]{15,15} )
~~~~

### 2) translate3d()
X축 벡터, Y축 벡터, Z축 벡터 값만큼 3D 이동.
with tx, ty and tz being the first, second and third translation-value parameters respectively.
~~~~
translate3d( <translation-value> , <translation-value> , <length> )
~~~~

### 3) translateZ()
Z축 방향으로 주어진 값만큼 이동
~~~~
translateZ( <length> )
~~~~

### 4) scale3d()
X축 벡터값, Y축 벡터값, Z축 벡터값만큼 3D 크기 변형
~~~~
scale3d( <number> , <number>, <number> )
~~~~

### 5) scaleZ()
Z축 벡터값만큼 3D 크기 변형
~~~~
scaleZ( <number> )
~~~~

### 6) rotate3d()
X축, Y축, Z축 방향벡터값과 각도값만큼 3D 회전. 방향벡터가 [0,0,0]처럼 정규화되면 회전이 적용되지 않는다.
~~~~
rotate3d( <number> , <number> , <number> , <angle> )
~~~~

### 7) rotateX()
X축 방향으로 회전
~~~~
rotateX( <angle> )
~~~~

### 8) rotateY()
Y축 방향으로 회전
~~~~
rotateY( <angle> )
~~~~

### 9) rotateZ()
Z축 방향으로 회전
~~~~
rotateZ( <angle> )
~~~~

### 10) perspective()
specifies a perspective projection matrix. This matrix scales points in X and Y based on their Z value, scaling points with positive Z values away from the origin, and those with negative Z values towards the origin. Points on the z=0 plane are unchanged. The parameter represents the distance of the z=0 plane from the viewer. Lower values give a more flattened pyramid and therefore a more pronounced perspective effect. For example, a value of 1000px gives a moderate amount of foreshortening and a value of 200px gives an extreme amount. The value for depth must be greater than zero, otherwise the function is invalid.
~~~~
perspective( <length> )
~~~~

<iframe height='265' scrolling='no' title='[CSS] perspective' src='//codepen.io/2yulrang/embed/wmejGV/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/2yulrang/pen/wmejGV/'>[CSS] perspective</a> by leeYura (<a href='https://codepen.io/2yulrang'>@2yulrang</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

<br><br>

# transform-origin

항목|내용
-----|-----
적용대상|블럭레벨, 인라인블럭레벨, table-row, table-row,group, table-header-group, table-footer-group, table-cell, table-caption
상속|X
초기값|50% 50%
%|바운딩 박스

## 1. 값
첫번째 값은 X축 방향, 두번째 값은 Y축 방향, 세번째 값은 Z축 방향에서 적용됨

- 하나의 값만 선언된 경우 : 두번째 값은 center로 계산됨
- 하나, 두개의 값을 선언한 경우 : 세번째 값은 0px로 계산됨

### \<percentage\>
바운딩 박스의 왼쪽 위 꼭지점을 기준으로 적용됨.
수평방향 오프셋은 바운딩박스의 width에, 수직방향 오프셋은 height에 비례하여 적용됨

### \<length\>
바운딩 박스의 왼쪽 위 꼭지점을 기준으로 적용됨.

### keyword
left (= 수평방향 0%), right (= 수평방향 100%),
top (= 수직방향 0%),  bottom (= 수직방향 100%),
center (= 수평방향 50%, 수직방향 50%)

<iframe height='265' scrolling='no' title='transform-origin' src='//codepen.io/2yulrang/embed/NgNLGy/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/2yulrang/pen/NgNLGy/'>transform-origin</a> by leeYura (<a href='https://codepen.io/2yulrang'>@2yulrang</a>) on <a href='https://codepen.io'>CodePen</a>.

</iframe>
