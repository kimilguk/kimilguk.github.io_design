### 화면구현과 UI디자인 실습자료
#### 실습진행 방식
- 폴더구조는 다음과 같이 구성 합니다. root(포워딩 index.html만 구성), home폴더(사용자단), admin(관리자단)
- 위 home, admin 폴더내부에 각각 사용될 css와 js, img 폴더를 배치 합니다.
- html및css,자바스크립트 테스트는 test.html 생성 후 실시 합니다.
- 스프링에서 사용할 사용자단 화면의 더미데이터는 dummy_index, dummy_list, dummy_view, dummy_write로 구현합니다.
- 사용자 화면으로 구현할 파일명은 index.html, board_list.html, board_view.html, board_write.html 입니다.
#### 정규표현식 - VS code 의 검색기능으로 확인
- 정규표현식 실습 내용: http://zvon.org/comp/r/tut-Regexp.html

```
정규식 소스
Hello, world!
who is who
$12$ \-\ $23$
Reqular expressions are powerful!!!
O.K.
```

- Page 1-2 : 기초(Regular Express 기본은 대소문자 구분함.)
- Page 3-4: ^who 캐럿 문자 사용 - ^는 소스 시작을 알리는 re 표현구문
- who$ 달러 문자 사용 - $는 문자열이 끝나는 것을 알리는 re 표현구문
- \$ \백슬래시 문자 사용 - 이스케이프는 표현구문이 아닌 문자 $를 찾는 re 표현구문
- ^\$, \$$ 실습.
- page 5: . 포인트문자 는 전체 문자를 검색.
- ^......, ......
- page 6: \. 으로 표현구문이 아닌 문자 .을 검색.
- \..\. 문자.과 문자.사이의 모든 문자를 포함해서 검색.
