# SELECT

```sql
SELECT 열이름 FROM 테이블이름 WHERE 조건;
```

- SELECT 열이름

: 질의 결과 추출되는 속성 리스트를 열거한다.

- FROM 테이블이름

: 질의에 어느 테이블이 사용되는지 열거한다.

- WHERE 조건

: 질의의 조건을 작성한다.

- **_여러 개의 열을 가져오고 싶을 때_**

: 쉼표로 구분하여 가져오면 된다.

ex)

```sql
SELECT 열이름1, 열이름2 FROM 테이블이름 WHERE 조건;
```

---

### WHERE(조건 사용하기)

```sql
SELECT 열이름1, 열이름2 FROM 테이블이름 WHERE 열이름1 = 'ahyun';

-- 열이름1이 ahyun인 것만 가져온다 라는 의미이다.
```

---

### 조건 연산자와 관계 연산자

`AND`와 `OR` 그리고 `>`, `<`, `=`를 이용해서 조건문에 활용하여 데이터를 출력할 수 있다.

---

### BETWEEN ... AND, IN(), LIKE 연산자

해당 범위 내의 데이터를 출력하고 싶을 때, 조건 연산자와 관계 연산자를 이용한다.

```sql
SELECT name, nickname FROM User WHERE age >= 10 AND age <= 20;

--age가 10세 이상부터 20세 이하인 데이터를 출력
```

위 SQL 문을 BETWEEN AND 연산자를 이용할 수도 있다.

```sql
SELECT name, nickname FROM User WHERE age BETWEEN 10 AND 20;

-- age가 10세 이상부터 20세 이하인 데이터를 출력
```

---

### 서브쿼리와 ANY, ALL, SOME 연산자

서브쿼리 : 쿼리문 안에 또 쿼리문이 들어있는 것

**ANY** : 여러 결과 중 한 가지만 만족해도 출력 (SOME이랑 같음)

**ALL** : 서브쿼리의 여러 결과를 모두 만족해야 출력

```sql
SELECT age FROM User
	WHERE age >= ANY (SELECT age FROM User WHERE name = '김%');

-- 성이 김씨인 사람보다 크거나 같은 나이 출력

SELECT age FROM User
	WHERE age >= ALL (SELECT age FROM User WHERE name = '김%');

-- 성이 김씨인 사람보다 크거나 같은 나이 출력
```

WHERE 문에 `=`을 붙이면 서브 쿼리 결과와 같은 값만을 출력한다.

`= ANY(서브쿼리)`는 `IN (서브쿼리)`와 동일하다.

---

### ORDER BY 절

결과가 출력되는 순서를 조절한다.

- 오름차순

  ```sql
  SELECT age FROM User ORDER BY name;

  SELECT age FROM User ORDER BY name ASC;

  -- 두 코드 동일한 순서로 값이 출력된다.
  ```

- 내림차순

  ```sql
  SELECT age FROM User ORDER BY name DESC;
  ```

여러가지 열로 출력되는 순서를 조절할 수도 있다.

```sql
SELECT age FROM User ORDER BY name ASC address DESC;

-- 이름 순으로 정렬하고, 이름이 같을 경우 주소 순으로 정렬한다.
```

`ORDER BY`는 `WHERE`절과 같이 사용해도 되고, 꼭 맨 뒤에 와야 한다.

또한, 꼭 필요할 때만 사용하는 것을 추천한다.

---

### DISTINCT

중복되지 않은 결과로 출력하고 싶을 때 쓰인다.

```sql
SELECT DISTINCT address FROM User WHERE age = 20;

-- 나이가 20인 사람의 주소를 출력한다.
-- 예를 들어 주소가 경기인 사람이 수백명이 될 수도 있으니, 그 결과를 경기라는 데이터 하나로 축소한다.
```

---

### LIMIT 절

출력되는 행의 개수를 제한하고 싶을 때 쓰인다.

```sql
SELECT age FROM User ORDER BY name LIMIT 5;

-- 이름 순으로 나이를 출력하는데, 5개의 행만 결과로 보여준다.
```

시작점(OFFSET)과 개수(LIMIT)으로 표현할 수 있다.

```sql
SELECT age FROM User ORDER BY name LIMIT 0, 5;

SELECT age FROM User ORDER BY name LIMIT 5 OFFSET 0;
```

---

### GROUP BY

그룹으로 묶는(grouping) 역할

집계 함수(aggregate function)와 함께 같이 쓰인다.

```sql
SELECT userId, SUM(amount) FROM Buytb GROUP BY userId;

-- userId와 amount의 합계를 출력하는데, userId로 그룹핑한다.
```

집계함수의 종류로는 `AVG(): 평균구하기`, `MIN(): 최솟값 구하기`, `MAX(): 최댓값 구하기`, `COUNT(): 행의 개수 세기`, `COUNT(DISTINCT): 행의 개수 세기(중복은 1개만 인정)`, `STDEV(): 표준편차 구하기`, `VAR_SAMP(): 분산 구하기` 가 있다.

- HAVING 절

  그룹핑 되어있는 결과에 조건을 더해 결과를 출력하고 싶을 때 쓰인다.

  ```sql
  SELECT userId, SUM(amount) FROM Buytb GROUP BY userId HAVING SUM(amount) > 1000;

  -- userId와 amount의 합계를 출력하는데, userId로 그룹핑한다. 그리고 SUM(amount)의 값이 1000 이상인 결과만 보고싶다.
  ```

---

# INSERT

값을 삽입하는 명령

```sql
INSERT [INTO] 테이블이름[(열1, 열2, ...)] VALUES (값1, 값2, ...);
```

---

### AUTO_INCREMENT

: 자동으로 1부터 증가하는 값을 입력하는 키워드

: 반드시 `PRIMARY KEY(기본키)` 또는 `UNIQUE(유일한 값)`으로 설정해야 한다.

: 데이터 형식이 숫자인 열에서만 사용 가능하다.

- 증가 값을 N으로 바꾸고 싶을 때

  ```sql
  -- 서버 변수인 @@auto_increment_increment 변수를 변경해야 한다.

  SET @@auto_increment_increment=N;
  ```

- 조건부 데이터 삽입 및 수정

  `INSERT IGNORE`을 이용하면 기본키가 중복되더라도 무시하고 넘어가며 오류 메시지만 출력한다.

  `ON DUPLICATE KEY UPDATE`는 기본키가 중복되지 않으면 일반 INSERT문처럼 동작하고, 기본키가 중복되면 UPDATE문을 실행한다.

---

# UPDATE

값을 수정하는 명령

```sql
UPDATE 테이블이름
SET 열1 = 값1, 열2 = 값2, ...
WHERE 조건
```

---

# DELETE

데이터를 행 단위로 삭제하는 명령

```sql
DELETE FROM 테이블이름 WHERE 조건;
```

DELETE 명령어는 트랜잭션 로그를 기록하는 작업을 하기 때문에 삭제하는 데 시간이 오래 걸린다.

DROP문은 테이블 자체를 삭제하고 트랜잭션 로그를 기록하지 않는다.

TRUNCATE문은 DELETE와 결과가 동일하지만 트랜잭션 로그를 기록하지 않아서 속도가 빠르다.

따라서 대용량 테이블 전체 내용을 삭제할 때는 `DROP`문을 사용하고, 테이블의 구조를 남겨놓고 싶은 경우에는 `TRUNCATE`문으로 삭제하는 것이 효율적이다.
