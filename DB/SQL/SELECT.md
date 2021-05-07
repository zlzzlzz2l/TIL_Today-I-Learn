# **SELECT**

```sql
SELECT 열이름 FROM 테이블이름 WHERE 조건;
```

- SELECT 열이름
  : 질의 결과 추출되는 속성 리스트를 열거한다.

- FROM 테이블이름
  : 질의에 어느 테이블이 사용되는지 열거한다.

- WHERE 조건
  : 질의의 조건을 작성한다.

**여러 개의 열을 가져오고 싶을 때**
: 쉼표로 구분하여 가져오면 된다.

ex)

```sql
SELECT 열이름1, 열이름2 FROM 테이블이름 WHERE 조건;
```

**WHERE(조건 사용하기)**

```sql
SELECT 열이름1, 열이름2 FROM 테이블이름 WHERE 열이름1 = 'ahyun';
# 열이름1이 ahyun인 것만 가져온다 라는 의미이다.
```