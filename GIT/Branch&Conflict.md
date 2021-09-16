# Branch & Conflict

### Branch

저장소를 복제하지 않고 동일한 효과를 누릴 수 있다. 즉, 같은 뿌리에서 나왔지만 서로 다른 역사를 쓰고 있는 버전을 말한다.

**만들어진 branch를 관찰 & 사용 방법**

- git log —all : 우리가 만든 모든 branch가 보인다.
- git log —all —graph : 우리가 만든 모든 branch가 보이면서 그래프로 시각화된다.
- git log —all —graph —oneline : 우리가 만든 모든 branch가 시각적으로 표현이 되면서 장황하게 나오지 않고 버전이 한 줄로 나온다.

**git branch**

branch가 어떤 게 있는지 목록화한다.

저장소를 만드는 순간에 master라는 기본 branch가 생성된다.

`*`는 가르키고 있는 branch를 나타낸다.

**git branch <브랜치명>**

브랜치명으로 브랜치가 만들어진다.

예를 들어,

버전4 (HEAD → master)

버전3 (abc, bcd, cde)

버전2

버전1

이 있다고 해보자. 여기서 abc, bcd, cde는 브랜치이다. 그리고 현재 master 브랜치를 가리키고 있다.

`git checkout abc`로 바꾸면 버전3에서 HEAD → abc로 바뀌고, 버전 3의 내용만 보이게 된다. 살짝 순간이동 느낌이다.

abc의 부모는 버전3이다. git checkout abc를 해준 후 작업하면 abc 브랜치만이 가지고 있는, 생성한 파일들이 보인다.

bcd 브랜치도 똑같이 버전3 자체가 부모고, `git checkout bcd`를 해주면 bcd만의 파일 관리가 시작된다. 여기서 abc에서 생성한 파일이나 수정본은 다른 브랜치에서 볼 수 없다.
