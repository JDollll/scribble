# 개발일기

개발하면서 끄적끄적

## Dev
- @PostConstruct
  - 의존성 주입이 이루어진 후 실행해야되는 method에 사용  
    ```java
    public class Test{
	  ...
	  @Autowired private GlobalFinder globalFinder;

	  public Test() {
	    // globalFinder.getDatabaseName();
	    // 여기서 호출때리면 아직 GlobalFinder가 불러와지지 않아서 에러 발생
	  }

	  @PostConstruct
	  public void testInit() {
	    // @PostConstruct 사용한 method에서 호출
	    globalFinder.getDatabaseName();
	  }
	  ...
    }
    ```
  - 참고
    - [Oracle Docs](https://docs.oracle.com/javaee/7/api/javax/annotation/PostConstruct.html)
    - [Stack Overflow](https://stackoverflow.com/questions/3406555/why-use-postconstruct)

## Git
  - Commit message 변경하기
    - push까지 했을경우
      - vi 에디터 사용
      - `git rebase HEAD&#126;1 -i`
      - 나오는 창에서 i 누르면 insert 모드로 변경됨
      - pick을 reword로 변경
      - esc 키 누르고 `:wq` 입력
      - commit message 수정
      - esc 키 누르고 `:wq` 입력
      - `git push --force` 강제로 푸쉬
        - 근데 강제푸쉬 하는거 안좋다고 들었음... ㅠㅠ


