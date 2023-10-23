### **Slow Query**

특정 쿼리가 실행되는 데 있어서, 평균적으로 오랜 시간이 걸리는 경우를 말한다.

### MySQL

my.cnf 파일에 아래 설정파일을 추가하여 슬로우 쿼리를 추적할 수 있다.

```bash
[mysqld]
slow_query_log_file=/data/mysqldb_logs/slow/mysql-slow-query.log /* 슬로우쿼리가 파일로 들어갈 경로 지정 */
long_query_time=2 /* 몇초 이상의 쿼리를 슬로우 쿼리로 만들지 파라미터 값 지정 */
```

MySQL 콘솔에서 다음과 같은 쿼리로 설정을 확인할 수 있다.
```bash
show global variables like 'long_query_time';
```