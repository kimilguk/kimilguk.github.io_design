### 화면구현과 UI디자인 실습자료
#### 실습진행 방식
- 폴더구조는 다음과 같이 구성 합니다. root(포워딩 index.html만 구성), home폴더(사용자단), admin(관리자단)
- 위 home, admin 폴더내부에 각각 사용될 css와 js, img 폴더를 배치 합니다.
- html및css,자바스크립트 테스트는 test.html 생성 후 실시 합니다.
- 스프링에서 사용할 사용자단 화면의 더미데이터는 dummy_index, dummy_list, dummy_view, dummy_write로 구현합니다.
- 사용자 화면으로 구현할 파일명은 index.html, board_list.html, board_view.html, board_write.html 입니다.
- VS code에서 깃 사용시 아이디/암호는 [윈도우 자격증명]에 저장 되기 때문에, 공용PC에서는 깃자격만 제거
#### 정규표현식 - VS code 의 검색기능으로 확인
- 정규표현식 실습 내용: http://zvon.org/comp/r/tut-Regexp.html

```
정규식 소스
Hello, world!
who is who
$12$ \-\ $23$
Reqular expressions are powerful!!!
O.K.
How do you do?
ABCDEFGHIJKLMNOPQRSTUVWXYZ
abcdefghijklmnopqrstuvwxyz 0123456789
월요일 화요일 수요일 목요일 금요일 토요일 일요일
aabc abc bc acb
-@-***--"*"--*****-@@-
<div>test</div><div>test2</div>
```
- #===정규표현식 패턴기본=============================
- Page 1-2 : 기초(Regular Express 기본은 대소문자 구분함.)
- #위치와 이스케이핑===============================
- Page 3-4: ^who 캐럿 문자 사용 - ^는 소스 시작을 알리는 re 표현구문
- who$ 달러 문자 사용 - $는 문자열이 끝나는 것을 알리는 re 표현구문
- \$ \백슬래시 문자 사용 - 이스케이프는 표현구문이 아닌 문자 $를 찾는 re 표현구문
- ^\$, \$$ , \n\n(찾을문자) -> \n(바꿀문자)실습.
- #===모든문자=======================================
- Page 5: . 포인트문자 는 전체 문자를 검색.
- ^......, ......
- Page 6: \. 으로 표현구문이 아닌 문자 .을 검색.
- \..\. 문자.과 문자.사이의 모든 문자를 포함해서 검색.
- #===특정문자=======================================
- Page 7: [] bracket 대괄호문자. 문장내부 포함된 1개 문자를 검색 [o]
- [dH]. 는 d문자 H문자 그리고, 문자 1개 결합된 2개의 문자 검색.
- [owy][yow] 는 2개의 문자를 검색.
- Page 8: - Dash 대시문자. [C-K] = [CDEFGHIJK], [2-6] 단, 오름차순정렬로 해야 함.
- Page 9: [^CDghi45] 대괄호 안에 캐럿이 있다면, 내용선택에서 반대inverse=제와하고 검색.
- #===서브패턴=======================================
- Page 10: ()괄호는 여러문자열 검색. (월요일|화요일|금요일) => 개선된 re표현은 (월|화|금)요일
- (월|화|금).일 처럼 와일드 카드 문자 .을 사용할 수 도 있음.
- #===수량자1(가장중요)=======================================
- Page 11-12: *, +, ? 어떤 패턴의 범위를 구하는 re구문
- a*b : a가 0개 이상 이고, b로 끝나는 내용 검색.
- a+b : a가 1개 이상 이고, b로 끝나는 내용 검색.
- a?b : a가 1개 이하 이고, b로 끝나는 내용 검색.
- .*  : 모든문자가 0개 이상인 니용 검색.
- -A*-: -로 시작하고 A가 0~n개 까지, -로 끝나는 내용 검색.
- Page 13: \*+ *문자가 1개 이상 내용 검색
- -@*- : -로 시작하고, @가 0개 이상인 -로 끝나는 내용 검색.
- -@+- : -로 시작하고 @가 1개 이상인 -로 끝나는 내용 검색.
- -@?- : -로 시작하고 @가 1개 이하인 -로 끝나는 내용 검색.
- Page 14: [^ ]+ 공백을 뺀 문자가 1개 이상인 내용 검색.
- Page 15: -\*?\*\*?\*? : -로 시작하고, *가 1개~4개 까지 존재하는 내용 검색
- .{5}, [a-z]{3,} : 모든문자중 5글자만 선택, 소문자a~z문자중 3개 이상글자만 선택.
- Page 16-17: *, +, ? 패턴을 {} 로 대체해서 선택가능.
- AB*A = AB{0,}A : A로 시작하고 B가 0개 이상인 A로 끝나는 내용 검색
- AB+A = AB{1,}A : A로 시작하고 B가 1개 이상인 A로 끝나는 내용 검색
- AB?A = AB{0,1}A : A로 시작하고 B가 1개 이하인 A로 끝나는 내용 검색
- r.* = r로 시작하고 모든 문자가 0개 이상인 내용 검색
- r.*? = r로 시작하고 모든 문자가 0개인 내용 검색
- r.+ = r로 시작하고 모든 문자가 1개 이상인 내용 검색
- r.+? = r로 시작하고, 모든 문자가 1개인 내용 검색
- <div>.+?</div> : 사용되는 방식확인
- r.?? = r로 시작하고, 모든 문자가 0개인 내용 검색