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

### Collections.emptyList()
  - 프로젝트 진행하다보니 어느날 모든 list 생성 부분이 Collections.emptyList()로 변경되어있는걸 발견!  
    - 되던거 안되고 exception 계속 뜨고 ㅠㅠ...
    - 프로젝트 내에 모든 list 생성부분이 이걸로 바껴있던데... 다시 돌려놔줘요 ㅠㅠ
  - Collections.emptyList()는 그냥 비어있는 list를 생성함    
  - AbstractList를 상속하고 있고 add(), addAll() 메소드도 호출이 가능하지만 사용할 수 없도록 예외 던짐
  - 진짜 그냥 말그대로 __비어있는 리스트__ 인거!
    - 그냥 딱 비어있는 list를 리턴해야될 경우에 사용해야됨
    - 무턱대고 썼다가는 add, get 등 우리가 써야될 메소드도 못쓰고 되던거 안되고 exception 발생함

### ibatis CLOB Select, Insert
  - CLOB 데이터를 insert 혹은 select 해올때 처리
  - Insert
    ```xml
      <insert id="" parameterClass="">
        INSERT INTO TABLE VALUES (#param:CLOB#)
      </insert>
    ```
  - Select
    - resultMap 선언 및 select
      ```xml
      <resultMap class="egovMap" id="resultId">
        <result property="propertyNm" column="columnName" jdbcType="CLOB" javaType="java.lang.String"/>
      </resultMap>

      <select id="" parameterClass="" resultClass="" resultMap="resultId">
        SELECT columnName FROM TABLE WHERE ...
      </select>
      ```


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

