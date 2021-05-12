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
