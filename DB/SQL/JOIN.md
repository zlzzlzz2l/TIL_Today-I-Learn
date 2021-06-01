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
