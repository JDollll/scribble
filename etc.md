# Etc

### Sublime Text
- sql insert문 내보냈는데 날짜들 골라내야되서(insert할때 오류나 ㅠㅠ) 구글링 해보다가 찾은 결과
- 내가 직면한 문제
```sql
INSERT INTO TABLE (...) VALUES 
  (..., ..., '2021-01-01 10:34:34', ..., ...),
  (..., ..., '2021-01-01 11:31:01', ..., ...),
  (..., ..., '2021-01-01 12:35:05', ..., ...),
  (..., ..., '2021-01-01 13:32:08', ..., ...),

  ...

```
- 날짜가 저렇게 되있으니 insert 할 때 `date format picture ends before converting entire input string` 오류발생
- 고민하다가 저런 형식의 데이터를 다 SYSDATE로 바꿔버리자 생각함
  - 날짜가 중요한 데이터들이 아니라서 ㅎㅎ
- 찾기 또는 바꾸기 할때 : '2021(.\*?)' 이렇게 찾으니까 딱 '2021-XX-XX XX:XX:XX' 만 찾아짐
  - '2021 + 모든것 + ' 찾겠다!
- 한방에 SYSDATE로 바꿈
- 꿀
