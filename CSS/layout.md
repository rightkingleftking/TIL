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
~~~

# 2단 레이아웃 구분선
## float 활용
~~~css
/*컨텐츠의 border를 이용해 구분선을 추가 하는 방법은 
컨텐츠가 최소 길이에 못미치는 경우 구분선이 footer까지 내려오지 않음*/

html, body, .wrap {
  height: 100%;
}

.header {
  height:100px;
  background-color: lightgreen;
}

.container {
  position: relative;
  width: 800px;
  padding: 100px 0;
  margin: -100px auto;
  box-sizing: border-box;
  min-height: 100%;
}

.container:after {
  display: block;
  clear: both;
  content: '';
}

.content {
  float: left; 
  width: 500px; 
  height: 300px;
  background-color: lightsalmon;
}

.aside {
  float: left; 
  width: 300px; 
  height: 300px;
  background-color: lightseagreen;
}

.aside:after { /*구분선 가상요소*/
  position: absolute;
  top: 100px; 
  right: 300px; /*aside의 width*/
  bottom: 100px;
  width: 1px;
  background-color: black;
  content: '';
}

.footer {
  height:100px;
  background-color: cornflowerblue;
}
~~~
## table-cell 활용
~~~css
html, body, .wrap {
  height: 100%;
}

.header {
  height:100px;
  background-color: lightgreen;
}

.container {
  display: table;
  table-layout: fixed; /*창 크기 변경시 컨텐츠 크기 고정*/
  width: 800px;
  padding: 100px 0;
  margin: -100px auto;
  box-sizing: border-box;
  min-height: 100%;
}

.content {
  display: table-cell;
  width: 500px; 
  background-color: lightsalmon;
  border-right: 1px solid black;
}

.aside {
  display: table-cell;
  width: 300px; 
  background-color: lightseagreen;
}

.footer {
  height:100px;
  background-color: cornflowerblue;
}
~~~
