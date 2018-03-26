# WAI-ARIA<br>(Web Accessibility Initiative Accessible Rich Internet Application)

다이나믹한 액션 UI에 대응하기 위한 접근성 정보를 제공하는 기술

WAI-ARIA를 쓰기에 앞서, **기본 마크업에 충실할것!**





## WAI-ARIA의 구성 요소

- 역할

- 상태

- 속성



<br><br>



### 1.역할

#### 1) 추상 역할 (Abstract Roles)

하위 역할의 개념을 정의하기 위한 상위 개념의 역할. **요소에 직접 지정할 수 없다.**



- command

- composite

- input

- landmark

- range

- roletype

- section

- sectionhead

- select

- structure

- widget

- window



<br>



#### 2) 위젯 역할 (Widget Roles)

사용자와 상호작용하는 독립적인 인터페이스의 역할



역할    |설명    |예시
-------|--------|-------
**alert**            |실시간 알림 메시지    |[페이지 이동 알림창](https://niawa.github.io/ARIA/15.%20loading/index.html), [실시간 유효성검사](https://niawa.github.io/ARIA/19.%20realtime-feedback/index.html)
alertdialog    |알림메시지가 들어있는 다이얼로그. 초기 포커스가 다이얼로그 내 요소에 위치|
button         |버튼 요소    |[버튼](https://niawa.github.io/ARIA/05.%20button/index.html)
checkbox     |복수 선택 가능한 true / false 입력요소    |[체크박스](https://niawa.github.io/ARIA/07.%20checkbox/index.html)
**dialog**         |사용자 인터랙션 애플리케이션 창    |[타임 세션](https://niawa.github.io/ARIA/13.%20time-limit/time-limit-aria.html)
gridcell        |그리드 셀|
link             |링크 요소|
log             |정보가 로깅되는 라이브 영역|
marquee      |자주 바뀌는 보조 정보 라이브 영역|
menuitem    |메뉴나 메뉴바 그룹에 있는 메뉴 항목|[드롭다운메뉴](https://niawa.github.io/ARIA/14.%20dropdown-menu/index.html), [네비게이션 메뉴바](https://www.w3.org/TR/wai-aria-practices/examples/menubar/menubar-1/menubar-1.html)
menuitemcheckbox    |복수 선택 가능한 true / false 메뉴 항목|
menuitemradio         |복수 선택 불가능한 true / false 메뉴 항목|
option           |select 목록에 있는 항목    |[콤보박스](https://niawa.github.io/ARIA/21.%20combobox/index.html)
progressbar    |작업의 진행 상태를 나타내는 요소|
radio             |복수 선택 불가능한 true / false 요소    |[라디오버튼](https://niawa.github.io/ARIA/06.%20radio-button/index.html)
scrollbar         |뷰 영역 안에서 콘텐츠 스크롤을 제어하는 요소|
slider             |주어진 범위 값 내에서 선택하는 입력 요소|
spinbutton      |사용자가 별도의 옵션 중에 선택할 수 있는 요소|
status            |덜 중요한 정보 컨테이너|
**tab**                |탭 요소|[탭](https://niawa.github.io/ARIA/01.%20tab-ui/index.html), [비주얼 슬라이드(탭)](https://niawa.github.io/ARIA/20.%20carousel/index.html)
**tabpanel**         |탭과 관련한 요소를 포함하는 컨테이너    |[탭, 탭 패널](http://www.oaa-accessibility.org/examplep/tabpanel1/)
textbox          |텍스트 입력 요소|
timer             |경과 시간이나 남은 시간을 나타내는 라이브 영역|
tooltip            |요소의 내용을 설명하는 팝업 요소    |[툴팁](https://niawa.github.io/ARIA/10.%20tooltip/index.html)
treeitem          |접거나 펼칠수 있는 트리 항목|



다른 것들을 포함하는 container 역할을 하는 widget



역할         |설명        |예시
------------|--------------------|-----------
**combobox**  |콤보박스 요소|[자동완성](https://niawa.github.io/ARIA/02.%20autocomplete/index.html), [콤보박스](https://niawa.github.io/ARIA/21.%20combobox/index.html)
grid           |테이블 형태의 데이터 인터랙티브 컨트롤|
**listbox**       |목록 항목 그룹    |[콤보박스](https://niawa.github.io/ARIA/21.%20combobox/index.html)
menu        |선택 목록 위젯    |[드롭다운메뉴](https://niawa.github.io/ARIA/14.%20dropdown-menu/index.html), [네비게이션 메뉴바](https://www.w3.org/TR/wai-aria-practices/examples/menubar/menubar-1/menubar-1.html)
menubar    |화면에 수평으로 표시되는 메뉴바 요소    |[드롭다운메뉴](https://niawa.github.io/ARIA/14.%20dropdown-menu/index.html), [네비게이션 메뉴바](https://www.w3.org/TR/wai-aria-practices/examples/menubar/menubar-1/menubar-1.html)
radiogroup |라디오 버튼 그룹    |[라디오버튼](https://niawa.github.io/ARIA/06.%20radio-button/index.html)
tablist        |탭 요소 목록    |[비주얼 슬라이드(탭)](https://niawa.github.io/ARIA/20.%20carousel/index.html)
tree          |접거나 펼칠 수 있는 트리 구조의 목록|
treegrid     |행을 접었다 펼 수 있는 그리드|


<br>



#### 3) 문서 구조 역할 (Document Roles)

웹 페이지의 문서 구조를 나타내는 역할

인터랙션이 없다는 점에서 위젯 역할과 구분됨



역할         |설명        |예시
------------|------------|---------
article                |독립적인 부분을 구성하는 요소로 이루어진 페이지 섹션|
columnheader    |열의 헤더 정보가 들어있는 셀 영역|
definition           |용어나 개념의 정의를 나타내는 영역|
**document**          |웹이 아닌 문서로 선언된 정보가 들어있는 영역|
group               |요소 등을 모아놓은 영역|[다중폼](https://niawa.github.io/ARIA/04.%20multi-group/index.html), [체크박스](https://niawa.github.io/ARIA/07.%20checkbox/index.html)
heading            |각 섹션의 헤딩 영역|
img                  |이미지 컨테이너 영역|
list                   |목록 항목 그룹|
listitem             |목록이나 디렉토리의 항목|
math                |수학적 표현을 나타내는 요소|
note                |콘텐츠에 삽입되거나 보조적으로 쓰인 콘텐츠 섹션|
**presentation**      |접근성이 매핑되지 않는 보여주기 요소|
region              |페이지에서 중요한 내용을 담긴 인지 영역    |[비주얼 슬라이드](https://niawa.github.io/ARIA/20.%20carousel/index.html)
~~row~~                  |그리드에서 셀의 행|
~~rowgroup~~          |그리드에서 행의 그룹|
~~rowheader~~         |그리드에서 행의 헤더 셀|
separator          |콘텐츠의 섹션, 메뉴 항목의 그룹 구분자|
toolbar             |작은 기능 버튼 모음|

<br>



#### 4) 랜드마크 역할 (Landmark Roles)

웹 페이지의 탐색을 용이하게 하기 위한 주요 영역을 나타내는 역할





역할    |설명    |예시
--------|---------|--------
**application**    |    |
**banner**    |페이지가 아닌 사이트와 관련한 내용(사이트·스폰서 로고, 사이트 검색도구)을 포함|
complementary    |    |
contentinfo    |    |
form    |    |
**main**    |    |
navigation    |    |[드롭다운메뉴](https://niawa.github.io/ARIA/14.%20dropdown-menu/index.html), [페이지 네비게이터](https://niawa.github.io/ARIA/18.%20page-navigator/index.html)
search    |    |

<br>



<div class="alert alert-info">센스리더에서 랜드마크 이동은 J 키로 가능하다</div>



<br>



https://www.w3.org/WAI/PF/aria/rdf_model.svg



[참고 - W3C](https://www.w3.org/TR/wai-aria/roles#command)



<br>



----------------------------



### 2. 상태

역할을 가진 요소의 현재 상태에 대해 설명함.



<table>

<tr>

<th>분류<br>(속성)</th>

<th>상태</th>

<th>설명</th>

<th>값</th>

<th>역할</th>

<th>예시</th>

</tr>

<tr>

<th rowspan="7">Widget</th>

<td>[aria-checked](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-checked)</td>

<td>체크된 상태</td>

<td>true / false / mixed</td>

<td>option, radio, checkbox...</td>

<td>[라디오버튼](https://niawa.github.io/ARIA/06.%20radio-button/index.html), [체크박스](https://niawa.github.io/ARIA/07.%20checkbox/index.html)</td>

</tr>

<tr>

<td>[**aria-disabled**](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-disabled)</td>

<td>요소의 비활성/활성</td>

<td>true / false</td>

<td>all</td>

<td>&nbsp;</td>

</tr>

<tr>

<td>[**aria-expanded**](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-expanded)</td>

<td>요소의 확장 상태</td>

<td>true / false / undefined</td>

<td>tree, menu, list...</td>

<td>[콤보박스](https://niawa.github.io/ARIA/21.%20combobox/index.html)</td>

</tr>

<tr>

<td>[**aria-hidden**](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-hidden)</td>

<td>요소의 숨김 여부</td>

<td>true / false</td>

<td>all</td>

<td>[에러메시지(꾸밈요소)](https://niawa.github.io/ARIA/08.%20error-message/index.html), [툴팁](https://niawa.github.io/ARIA/10.%20tooltip/index.html), [꾸밈요소](https://niawa.github.io/ARIA/16.%20special-charactor/index.html), [비주얼 슬라이드](https://niawa.github.io/ARIA/20.%20carousel/index.html), [콤보박스](https://niawa.github.io/ARIA/21.%20combobox/index.html)</td>

</tr>

<tr>

<td>[aria-invalid](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-invalid)</td>

<td>응용 프로그램에서 예상되는 형식을 준수하지 않는 입력 값</td>

<td>true / false / grammar / spelling</td>

<td>all</td>

<td>[에러메시지](https://niawa.github.io/ARIA/08.%20error-message/index.html), [유효성 검사](https://niawa.github.io/ARIA/17.%20form-label/index.html)</td>

</tr>

<tr>

<td>[aria-pressed](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-pressed)</td>

<td>눌려져 있는 상태</td>

<td>true / false / mixed</td>

<td>button</td>

<td>[토글버튼](https://www.w3.org/TR/wai-aria-practices/examples/button/button.html)</td>

</tr>

<tr>

<td>[**aria-selected**](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-selected)</td>

<td>선택된 상태</td>

<td>true / false / undefined</td>

<td>row, tab, treeitem...</td>

<td>[비주얼 슬라이드(탭)](https://niawa.github.io/ARIA/20.%20carousel/index.html)</td>

</tr>

<tr>

<th>Live Region</th>

<td>[aria-busy](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-busy)</td>

<td>요소와 그 하위 트리가 현재 업데이트되고 있는지 여부</td>

<td>true / false</td>

<td>all</td>

<td>&nbsp;</td>

</tr>

<tr>

<th>Drag-and-Drop</th>

<td>[aria-grabbed](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-grabbed)</td>

<td>드래그앤 드롭 요소의 드래그 상태</td>

<td>true / false / undefined</td>

<td>all</td>

<td>&nbsp;</td>

</tr>

</table>



<br>



-------------------------------



### 3. 속성

<table>
<tr>
<th>분류</th>
<th>속성</th>
<th>설명</th>
<th>값</th>
<th>역할</th>
<th>예시</th>
</tr>

<tr>
<th rowspan="13">Widget</th>
<td>[aria-autocomplete](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-autocomplete)</td>
<td>자동완성 지원 여부</td>
<td>inline / list / both / none</td>
<td>combobox, textbox</td>
<td>[자동완성](https://niawa.github.io/ARIA/02.%20autocomplete/index.html), [콤보박스](https://niawa.github.io/ARIA/21.%20combobox/index.html)</td>
</tr>

<tr>
<td>[aria-haspopup](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-haspopup)</td>
<td>팝업 메뉴나, 하위 레벨 메뉴 존재 여부</td>
<td>true / false</td>
<td>all</td>
<td>[자동완성](https://niawa.github.io/ARIA/02.%20autocomplete/index.html), [콤보박스](https://niawa.github.io/ARIA/21.%20combobox/index.html)</td>
</tr>

<tr>
<td>[**aria-label**](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-label)</td>
<td>현재 요소의 이름을 나타내는 값 설정</td>
<td>true / false</td>
<td>all</td>
<td>[다중폼](https://niawa.github.io/ARIA/04.%20multi-group/index.html), [콤보박스(버튼)](https://niawa.github.io/ARIA/21.%20combobox/index.html)</td>
</tr>

<tr>
<td>[aria-level](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-level)</td>
<td>계층 구조에서 요소의 레벨 설정</td>
<td>integer</td>
<td>grid, heading, listitem, row, tablist</td>
<td>&nbsp;</td>
</tr>

<tr>
<td>[aria-multiline](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-multiline)</td>
<td>텍스트 박스에 여러줄을 입력할 수 있는지 여부 설정</td>
<td>true / false</td>
<td>textbox</td>
<td>&nbsp;</td>
</tr>

<tr>
<td>[aria-orientation](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-orientation)</td>
<td>요소와 화면 방향 가로/세로 설정</td>
<td>vertical / horizontal</td>
<td>scrollbar, separator, slider</td>
<td>&nbsp;</td>
</tr>

<tr>
<td>[aria-required](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-required)</td>
<td>필수 입력 항목 설정</td>
<td>true / false</td>
<td>combobox, gridcell, listbox, radiogroup, spinbutton, textbox, tree</td>
<td>[필수 입력 항목](https://niawa.github.io/ARIA/11.%20required/index.html), [유효성 검사](https://niawa.github.io/ARIA/17.%20form-label/index.html)</td>
</tr>

<tr>
<td>[aria-readonly](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-readonly)</td>
<td>읽기 전용 설정</td>
<td>true / false</td>
<td>grid, gridcell, textbox</td>
<td>[콤보박스](https://niawa.github.io/ARIA/21.%20combobox/index.html)</td>
</tr>

<tr>
<td>[aria-multiselectable](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-multiselectable)</td>
<td>여러 개 선택 가능한지 설정</td>
<td>true / false</td>
<td>grid, listbox, tablist, tree</td>
<td>&nbsp;</td>
</tr>

<tr>
<td>[aria-valuemax](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-valuemax)</td>
<td>범위의 최댓값 설정</td>
<td>number</td>
<td>range</td>
<td>&nbsp;</td>
</tr>

<tr>
<td>[aria-valuemin](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-valuemin)</td>
<td>범위의 최솟값 설정</td>
<td>number</td>
<td>range</td>
<td>&nbsp;</td>
</tr>

<tr>
<td>[aria-valuenow](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-valuenow)</td>
<td>범위의 현재값 설정</td>
<td>number</td>
<td>range</td>
<td>&nbsp;</td>
</tr>

<tr>
<td>[aria-valuetext](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-value-text)</td>
<td>aria-valuenow를 대체하는 텍스트 설정</td>
<td>string</td>
<td>range</td>
<td>&nbsp;</td>
</tr>

<tr>
<th rowspan="3">Live Region</th>
<td>[aria-atomic](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-atomic)</td>
<td>aria-relevant 속성으로 정의된 알림 방식에 따라 변경 요소의 공개 여부를 설정.</td>
<td>true / false</td>
<td>all</td>
<td>&nbsp;</td>
</tr>

<tr>
<td>[**aria-relevant**](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-relevant)</td>
<td>요소가 변경될 때 어떤 알림을 받을 것인지 설정</td>
<td>additions / removals / text / all</td>
<td>all</td>
<td>[자동완성](https://niawa.github.io/ARIA/02.%20autocomplete/index.html)</td>
</tr>

<tr>
<td>[**aria-live**](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-live)</td>
<td>요소가 업데이트 될것임을 표시, 업데이트 종류 설명</td>
<td>off / polite / assertive</td>
<td>all</td>
<td>[자동완성](https://niawa.github.io/ARIA/02.%20autocomplete/index.html), [유효성 검사](https://niawa.github.io/ARIA/17.%20form-label/index.html)</td>
</tr>

<tr>
<th>Drag & Drop</th>
<td>[aria-dropeffect](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-dropeffect)</td>
<td>드래그를 끝냈을 때 어떤 기능이 수행되는지 설정</td>
<td>copy, move, link, execute, popup, none</td>
<td>all</td>
<td>&nbsp;</td>
</tr>

<tr>
<th rowspan="8">Relationship</th>
<td>[**aria-labelledby**](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-labelledby)</td>
<td>현재 엘리먼트의 이름을 나타내는 요소들의 id 설정</td>
<td>참조 id</td>
<td>all</td>
<td>[다중폼](https://niawa.github.io/ARIA/04.%20multi-group/index.html)</td>
</tr>

<tr>
<td>[aria-activedescendant](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-activedescendant)</td>
<td>복합 위젯에서 현재 활성화된 자손의 id 설정</td>
<td>참조 id</td>
<td>composite, group, textbox</td>
<td>[콤보박스](https://niawa.github.io/ARIA/21.%20combobox/index.html)</td>
<tr>

<td>[**aria-controls**](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-controls)</td>
<td>현재 요소가 다른 요소를 조작하는 경우 해당 요소의 id 설정</td>
<td>참조 id</td>
<td>all</td>
<td>[탭](https://niawa.github.io/ARIA/01.%20tab-ui/index.html), [비주얼 슬라이드(탭)](https://niawa.github.io/ARIA/20.%20carousel/index.html)</td>
</tr>

<tr>
<td>[aria-flowto](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-flowto)</td>
<td>콘텐츠 읽기 순서에서 다음 요소 지정</td>
<td>참조 id</td>
<td>all</td>
<td>&nbsp;</td>
</tr>

<tr>
<td>[**aria-describedby**](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-describedby)</td>
<td>요소를 설명하는 다른 요소의 id 설정</td>
<td>참조 id</td>
<td>all</td>
<td>[에러메시지](https://niawa.github.io/ARIA/08.%20error-message/index.html), [툴팁](https://niawa.github.io/ARIA/10.%20tooltip/index.html), [플레이스홀더](https://niawa.github.io/ARIA/11.%20required/index.html), [유효성 검사](https://niawa.github.io/ARIA/17.%20form-label/index.html)</td>
</tr>

<tr>
<td>[aria-posinset](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-posinset)</td>
<td>목록, 트리 항목이 DOM에 없는 경우, 현재 요소의 개수나 위치 설정</td>
<td>integer</td>
<td>listitem, option</td>
<td>&nbsp;</td>
</tr>

<tr>
<td>[aria-setsize](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-setsize)</td>
<td>목록, 트리 항목이 DOM에 없는 경우, 현재 항목의 개수 설정</td>
<td>integer</td>
<td>listitem, option</td>
<td>&nbsp;</td>
</tr>

<tr>
<td>[aria-owns](https://www.w3.org/TR/2014/REC-wai-aria-20140320/states_and_properties#aria-owns)</td>
<td>DOM 계층구조를 나타낼 수 없는 곳에서 요소들간의 시각,기능,상황적 부모-자식 관계를 정의하기 위해 id 설정</td>
<td>참조 id</td>
<td>all</td>
<td>[콤보박스](https://niawa.github.io/ARIA/21.%20combobox/index.html)</td>
</tr>

</table>



<br><br><br>



-----------------------------------





예시 출처



- https://github.com/niawa/ARIA <예제로 살펴보는 WAI-ARIA> 예제코드 내용

- https://www.w3.org/TR/wai-aria-practices







*** 굵게 표시된 텍스트는 센스리더에서 지원하는 것이 확인된 속성입니다. ( http://xvtech.com 참고 )**
