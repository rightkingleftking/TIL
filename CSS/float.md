# float 해제
- 부모요소에 height 부여
  - 값이 고정적이면 활용 가능
- 부모요소에 float속성 포함
  - 자신이 float속성을 가질 시 자식요소는 따로 해제처리를 안해줘도 된다는 선에서만 활용
- 부모요소에 overflow속성 변경(visible 제외)
  - 부모요소를 벗어나는 팝업과 같은 컨텐츠는 보이지 않을 수 있다는 단점
- 인접 형제요소에 clear
  - 빈 태그에 clear요소를 넣는 방법으로, 시맨틱하지 않음 -> 가상요소 사용
~~~css
.box_parent:after {
  display: block;
  clear: both;
  content: "";
}
