# Dev
그냥 개발하면서 새로 알게된거나 나중에 생각날만한거 주저리주저리

## JAVA
### @PostConstruct
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

## JS
### localStorage
  - 사용자 로컬에 데이터 보관
  - 저장, 삭제 가능
  - key, value 형식으로 저장함
  - 사이트, 브라우저 마다 저장됨

    ```javascript
    function func() {
      localStorage.setItem("save", "저장"); // 저장
      localStorage.getItem("save"); // 조회
      localStorage.removeItem("save"); // 해당 데이터 삭제

      localStorage.clear(); // 저장된거 전체 삭제	
    }
      
    ```

  - 근데 무조건 String으로 들어감
  - Object 담고싶으면 `JSON.stringify(); JSON.parse();` 적절히 쓰면됨 

