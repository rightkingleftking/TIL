# 최소높이 100% 설정하기
~~~css
html, body, .wrap {
  height: 100%; /* 퍼센트는 부모요소로부터 상속받기 때문에 부모요소에 모두 높이값을 설정해야함 */
}

.header {
  height:100px;
}

.container {
  padding: 100px 0; 
  margin: -100px auto;
  box-sizing: border-box;
  min-height: 100%;
  /*100%에 header와 footer의 영역을 포함시키기 위해 
  각 값만큼 패딩으로 띄워주고 마진으로 당긴 후 box-sizing바꾸기*/
}

.footer {
  height:100px;
}
