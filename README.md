# errorCheck
내가보려고만듬


mysql 유저 권한 주기 https://blusky10.tistory.com/362


DB 별 count

postgres, cubrid, oracle, mysql, tibero
```
  SELECT COUNT(*) FROM TABLE_NAME
```



DB별 pagination

POSTGRES
```
SELECT * from TABLE_NAME OFFSET 0 limit 20;
```
CUBRID
```
1. SELECT * FROM TABLE_NAME BETWEEN 1 AND 10;
2. SELECT * FROM TABLE_NAME LIMIT ?1,?2
```
OCRACLE 12버전 이전(ROWNUM 이용)
```
  SELECT *
	FROM
	    (
	        SELECT /*+ INDEX(T1 PK1) */
	            ROWNUM AS RNUM, T1.*
	        FROM
	            TABLE1 T1
	        WHERE
	            ROWNUM <= 200
	    )
	WHERE
	    101 <= RNUM
```
OCRACLE 12버전 이후(TOP-N QUERY 이용)
```
SELECT * FROM TABLE_NAME OFFSET 6 ROWS FETCH FIRST 5 ROWS ONLY;
```
MYSQL
```
SELECT * FROM TABLE_NAME LIMIT 0, 10
```
Tibero
```
oracle 12버전 이전
```
