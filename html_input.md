# input

## 0. global (공통)

### 1) [global attribute](https://www.w3.org/TR/html5/forms.html#attributes-common-to-form-controls)

- name : 폼 컨트롤의 name을 지정. 폼을 제출할 때 쓰인다. 빈 문자열이면 안됨.
- dirname :
- maxlength, minlength : 입력할 문자의 수를 제한
- disabled
- action
- method
- enctype, formenctype
- target, formtarget
- novalidate, formnovalidate
- autofocus
- autocomplete

<br><br>


## 1. type

### 1) [text](https://www.w3.org/wiki/HTML/Elements/input/text)

<iframe height='265' scrolling='no' title='[markup] input -  text' src='//codepen.io/yuuuuul/embed/PJpprv/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/yuuuuul/pen/PJpprv/'>[markup] input -  text</a> by yuuuuul (<a href='https://codepen.io/yuuuuul'>@yuuuuul</a>) on <a href='https://codepen.io'>CodePen</a>.

</iframe>



### (1) attribute

- list = 참조 ID
- pattern = 정규식
- placeholder = 문자열
- readonly = true / false
- required = true / false
- size = 음이 아닌 유효한 정수
- value = 문자열

<br>

### 2) password

<iframe height='265' scrolling='no' title='[markup] input - password' src='//codepen.io/yuuuuul/embed/PJpKEx/?height=265&theme-id=0&default-tab=html,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/yuuuuul/pen/PJpKEx/'>[markup] input - password</a> by yuuuuul (<a href='https://codepen.io/yuuuuul'>@yuuuuul</a>) on <a href='https://codepen.io'>CodePen</a>.

</iframe>


### (1) attribute

- pattern = 정규식
- placeholder = 문자열
- readonly = true / false
- required = true / false
- size = 음이 아닌 유효한 정수
- value = 문자열

<br>

## 3) radio

<iframe height='265' scrolling='no' title='[markup] input - radio' src='//codepen.io/yuuuuul/embed/yzMoQe/?height=265&theme-id=0&default-tab=html,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/yuuuuul/pen/yzMoQe/'>[markup] input - radio</a> by yuuuuul (<a href='https://codepen.io/yuuuuul'>@yuuuuul</a>) on <a href='https://codepen.io'>CodePen</a>.

</iframe>



### (1) attribute

- checked = true / false
- required = true / false
- value = 문자열

<br>



## 4) checkbox

<iframe height='265' scrolling='no' title='[markup] input - checkbox' src='//codepen.io/yuuuuul/embed/oGZeQq/?height=265&theme-id=0&default-tab=html,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/yuuuuul/pen/oGZeQq/'>[markup] input - checkbox</a> by yuuuuul (<a href='https://codepen.io/yuuuuul'>@yuuuuul</a>) on <a href='https://codepen.io'>CodePen</a>.

</iframe>



### (1) attribute

- checked = true / false
- required = true / false
- value = 문자열


<br><br><br>





# input 요소를 위한 css

## 1. :placeholder-shown

가상 클래스 선택자. placeholder가 보여질 때의 input을 선택한다


## 2. ::placeholder

가상 요소 선택자. placeholder 텍스트를 선택한다.



참고) https://css-tricks.com/almanac/selectors/p/placeholder/



<br>
