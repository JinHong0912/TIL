# 🚴🏻‍♂️#21.07.02 : CASE WHEN THEN ELSE END

분야  : SQL

💡**일일 실습 할 부분을 먼저 작성해서 알아 본다.**

[🌵 해야 하는 실습](#cc542a64-c591-41fc-a67b-2143a93b0358)

[1. CASE WHEN ~ THEN~ ELSE END](#f78a5301-d089-4228-bdf9-1db43fbf767d)

[2. MYSQL 예시](#dbbd857a-d79d-4109-b8c7-0a4056ac9a1d)

[3. 적용](#4852e870-1d7b-485f-8c8d-fe1296610773)

[QUERY 적용](#54e6a0ec-1050-4bb5-9e8d-14e93ebd6e4e)



### 🌵 해야 하는 실습

### 1. CASE WHEN ~ THEN~ ELSE END

-   JAVA의 IF ~ ELSE 문과 비슷한 CASE WHEN문이다.

```
CASE WHEN THEN ELSE END

## 형식 ##

CASE 컬럼명 | 표현식
	WHEN 조건식1 THEN 결과1
	WHEN 조건식2 THEN 결과2
	....................
	WHEN 조건식n THEN 결과n
	ELSE 결과
END 

## 조건문과 조건문 사이에는 콤마를 사용하지 않는다.
## CASE 문은 반드시 END로 끝내야 한다.
## CASE 표현식은 ANSI SQL 형식도 지원
## 결과 부분은 NULL을 사용해서는 안된다.
```

### 2. MYSQL 예시

```
# 1. 조건 X = Y 가 TRUE 일 경우 A 이고 그렇지 않으면 B
CASE WHEN X = Y THEN A ELSE B END
	
# 2 .조건 X < Y 가 TRUE 일 경우 A로, 조건 X = Y 일 경우엔 B 로 
# 그렇지 않으면 C로 변경

CASE 
		WHEN X < Y THEN A 
		WHEN X = Y THEN B
		ELSE C
END

# 3. XYZ 가 FOO 일 경우 MOO 로 변경, 그렇지 않으면 AOO로 변경
	
CASE XYZ
		WHEN 'FOO' THEN 'MOO'
		ELSE 'AOO'
END


```

### 3. 적용

```
# 1. 테이블 검색

SELECT tb_no,pwd FROM test_board;

## 적용

SELECT tb_no , pwd,
	CASE 
			WHEN pwd = '123' THEN 'Y'
			WHEN pwd = '111' THEN 'N'
			ELSE '?????'
	END AS PASSWD
FROM test_board LIMIT 10;


### UPDATE
UPDATE test_board SET pwd = 123 WHERE tb_no = 1;
UPDATE test_board SET pwd = 13213123 WHERE tn_no = 2;
UPDATE test_board SET pwd = 111 WHERE tb_no = 3;
```



