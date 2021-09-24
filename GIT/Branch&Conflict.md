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

---

### Merge & Conflict

![image](https://user-images.githubusercontent.com/48669011/133891077-5549e204-de66-4ea6-97fa-03bbf8d557cf.png)

위 사진은 부모 브랜치인 master를 기점으로 abc와 bcd 브랜치가 커밋된 상태이다. abc 브랜치에 있는 작업 내용이 master 브랜치의 내용과 합쳐지면 더 좋은 작업 내용이 될 거 같다. 이 때 쓰이는 게 `merge`이다.

![image](https://user-images.githubusercontent.com/48669011/133891082-4ae81f32-6c54-45c5-958e-4b533edb5644.png)

merge를 하기 위해서 abc와 master를 병합하여 새로운 버전을 만들어야 한다.

![image](https://user-images.githubusercontent.com/48669011/133891088-895e0ab6-068e-428b-a8fb-cfca8f61a4af.png)

여기서 브랜치 abc와 master의 원래 부모는 base라고 한다.

**서로 다른 파일 병합 방법**

예를 들어 a.txt와 b.txt가 존재한다. 

```
// a.txt

a입니다.

// b.txt

b입니다.
```

이 파일들은 master 브랜치에서 만들었고, abc 이라는 브랜치를 생성했다고 해보자.

git checkout abc 명령어를 이용하여 abc 브랜치로 이동한다. git branch로 선택된 브랜치가 abc로 변경된 걸 볼 수 있다.

abc 브랜치에서 a.txt의 내용을 변경했다.

```
// a.txt

a입니다.
내용을 수정합니다.
```

변경한 후, git add a.txt → git commit -m "a 수정"을 입력하면 abc 브랜치는 새로운 버전을 생성하게 된다.

이 때, abc 브랜치에서 수정한 내용을 master 브랜치에 다른 파일과 함께 병합하고 싶다면 일단 master 브랜치로 이동한다. 그 후 git merge abc를 해주면 병합된다.

즉,

1. master branch의 상태가 되어야 한다.
2. 병합하고 싶은 branch를 merge 명령어를 통해서 지정한다.

    ex) git merge abc