

부트시 sql 실행
------
```
spring.sql.init.mode: always
```
resources 의 data.sql 혹은 schema.sql 을 로딩시에 실행 시킨다. 

```
spring.jpa.hibernate.ddl-auto: create 
```
와 함께일 경우 sql 실행이 먼저 되고 ddl-auto: create 가 나중에 실행되어 데이터가 없어지는데 
```
spring.jpa.defer-datasource-initialization: true
```
를 추가 함으로써 sql 실행 순서를 조정할 수 있다.




* 

* Going Reactive with Spring, Coroutines and Kotlin Flow
https://spring.io/blog/2019/04/12/going-reactive-with-spring-coroutines-and-kotlin-flow


* spring-boot-kotlin-coroutines https://www.baeldung.com/kotlin/spring-boot-kotlin-coroutines


