상위태그 : [웹 접근성](https://github.com/rightkingleftking/TIL/#웹-접근성)
# Image Replacement
- 다양한 상황에 대비해 이미지 정보를 전달하기 위한 기법
- 사용처
  - 대체택스트가 너무 길 때
  - background-image 처리된 의미있는 이미지(ex. 고정적인 이미지를 한 곳에 모아 한 장의 이미지로 만들어서 처리하는 sprite image)
- 고려 사항
  - 시멘틱 마크업 -> 필요없는 요소를 마크업하지 않도록 유의
  - 화면에서 숨길 때에도 그 정보는 스크린리더가 인식해야함
# 프로모션 페이지
- 이미지가 통으로 되어 있는 경우, 각각의 정보를 마크업하고 화면에는 보이지 않도록 숨겨야함.
- 링크는 해당 위치에서 클릭되어야하기 때문에 링크를 제외한 나머지 태그들을 blind 처리해줌
- 링크마크업은 css를 이용해 위치를 화면상의 링크 이미지 위치와 일치하게 처리
## 화면에서 숨기기
- 스크린 리더가 인식 x
~~~css
visibility: hidden;
display: none;
size를 0로 초기화
~~~
- 스크린 리더가 인식하지만 성등 혹은 레이아웃에서 문제발생 가능
~~~css
opacity: 0; // 요소를 투명하게 함. 자리를 차지함
text-indent: -9999; // 전체레이어가 크게 잡힘(성능 이슈). -> 값을 100%로 수정. 첫 줄만 적용. 자리를 차지함
z-index:-1; // position 속성을 추가해야함(성능 이슈)
~~~
- 권장 (blind 클래스를 따로 두어서 적용)
~~~css
position: absolute;
width: 1px;
height: 1px;
clip:rect(0 0 0 0);
margin:-1px;
overflow: hidden;
~~~
