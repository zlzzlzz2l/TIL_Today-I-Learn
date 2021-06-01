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
