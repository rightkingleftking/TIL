# 인접형제선택자
~~~css
former_element + target_element { style properties }
~~~
지정한 요소(former_e) 바로 뒤에오는 형제요소(target_e)를 선택
## 활용
- 구분선으로 감싸져 나열된 연속적인 요소들 사이의 경계선 중복을 제거
~~~css
.menu-item + .menu-item .menu-link {
  margin-left: -1px;
}
~~~
### z-index 제어
- 선택된 메뉴를 표현시 위 활용에서 겹쳐진 경계선 때문에 다음 요소와의 경계선이 보이지 않는 현상 존재
- position을 relative로 바꿔줌으로써 z-index를 가장 최근에 수정한 것으로 처리하여 가장 위로 보내주기
- 활용이 필요한 예시
![z-index-example](https://user-images.githubusercontent.com/46833758/109167886-99f07c00-77c1-11eb-9780-a1d128ef8d2b.png)
