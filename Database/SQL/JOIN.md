# JOIN

2개 이상의 테이블을 묶어서 하나의 결과 테이블을 만드는 것을 의미한다.

---

# INNER JOIN(내부 조인)

```sql
SELECT <열 목록>
	FROM <첫 번째 테이블>
	INNER JOIN <두 번째 테이블>
	ON <조인될 조건>
[WHERE 검색조건];
```

조인에서 가장 많이 쓰인다.

---

# OUTER JOIN(외부 조인)

조인 조건을 만족하지 않는 행까지 포함하여 출력한다.

```sql
SELECT <열 목록>
	FROM <첫 번째 테이블>
	<LEFT / RIGHT> OUTER JOIN <두 번째 테이블(RIGHT 테이블)>
	ON <조인될 조건>
[WHERE 검색조건];
```

- LEFT OUTER JOIN

  결과가 조인 조건에 해당하지 않더라도 왼쪽 테이블의 모든 행을 출력한다.

- RIGHT OUTER JOIN

  결과가 조인 조건에 해당하지 않더라도 오른쪽 테이블의 모든 행을 출력한다.

---

# CROSS JOIN(상호 조인)

한쪽 테이블의 모든 행과 다른 쪽 테이블의 모든 행을 조인하는 것을 말한다.

상호 조인 결과 테이블의 행수는 두 테이블의 행수를 곱한 값이다.

```sql
SELECT <열 목록>
	FROM <첫 번째 테이블>
	CROSS JOIN <두 번째 테이블>
	ON <조인될 조건>
[WHERE 검색조건];
```

실제로 사용하게 되면 시스템이 다운되거나 디스크의 용량이 꽉 찰 수도 있다.

---

# SELF JOIN(자체 조인)

자기 자신과 자기 자신을 조인하는 것을 말한다.

```sql
SELECT <열 목록>
	FROM <테이블 이름>
	INNER JOIN <테이블 이름>
	ON <조인될 조건>
[WHERE 검색조건];
```

---

# UNION/UNION ALL

`UNION`은 두 쿼리의 결과를 행으로 합치는 연산자이다.

`UNION ALL`은 중복된 열까지 출력한다.

```sql
SELECT 문장1
	UNION [ALL]
SELECT 문장2
```

EX)

```sql
SELECT name, age FROM User
	UNION
SELECT bookname, price FROM Book

-- User 테이블의 name, age행과 Book 테이블의 bookname, price를 하나의 행으로 만든다.
```

위 예시와 같이 열의 개수가 같아야 하고 데이터 형식도 같아야 한다.

---

# NOT IN/IN

`NOT IN`은 첫 번째 쿼리의 결과 중에서 두 번째 쿼리에 해당하는 것을 제외하고 출력하는 연산자이다.

`IN`은 첫 번째 쿼리의 결과 중에서 두 번째 쿼리에 해당되는 것만 조회하는 연산자이다.

```sql
SELECT name, age FROM User
	WHERE age NOT IN (SELECT age FROM User WHERE age > 20);

-- 20세 이하인 사용자 이름과 나이를 출력한다.
```

```sql
SELECT name, age FROM User
	WHERE age IN (SELECT age FROM User WHERE age > 20);

-- 20세 이상인 사용자 이름과 나이를 출력한다.
```
