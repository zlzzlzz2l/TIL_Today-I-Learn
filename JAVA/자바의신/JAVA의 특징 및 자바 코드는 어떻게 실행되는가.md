## Contents

- <a href="https://github.com/zlzzlzz2l/TIL_Today-I-Learn/blob/main/JAVA/%EC%9E%90%EB%B0%94%EC%9D%98%EC%8B%A0/JAVA%EC%9D%98%20%ED%8A%B9%EC%A7%95%20%EB%B0%8F%20%EC%9E%90%EB%B0%94%20%EC%BD%94%EB%93%9C%EB%8A%94%20%EC%96%B4%EB%96%BB%EA%B2%8C%20%EC%8B%A4%ED%96%89%EB%90%98%EB%8A%94%EA%B0%80.md#jvm%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80"> JVM이란 무엇인가 </a>
- <a href="https://github.com/zlzzlzz2l/TIL_Today-I-Learn/blob/main/JAVA/%EC%9E%90%EB%B0%94%EC%9D%98%EC%8B%A0/JAVA%EC%9D%98%20%ED%8A%B9%EC%A7%95%20%EB%B0%8F%20%EC%9E%90%EB%B0%94%20%EC%BD%94%EB%93%9C%EB%8A%94%20%EC%96%B4%EB%96%BB%EA%B2%8C%20%EC%8B%A4%ED%96%89%EB%90%98%EB%8A%94%EA%B0%80.md#%EC%BB%B4%ED%8C%8C%EC%9D%BC-%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95"> 컴파일 하는 방법 </a>
- <a href="https://github.com/zlzzlzz2l/TIL_Today-I-Learn/blob/main/JAVA/%EC%9E%90%EB%B0%94%EC%9D%98%EC%8B%A0/JAVA%EC%9D%98%20%ED%8A%B9%EC%A7%95%20%EB%B0%8F%20%EC%9E%90%EB%B0%94%20%EC%BD%94%EB%93%9C%EB%8A%94%20%EC%96%B4%EB%96%BB%EA%B2%8C%20%EC%8B%A4%ED%96%89%EB%90%98%EB%8A%94%EA%B0%80.md#%EC%8B%A4%ED%96%89-%EB%B0%A9%EB%B2%95"> 실행하는 방법 </a>
- <a href="https://github.com/zlzzlzz2l/TIL_Today-I-Learn/blob/main/JAVA/%EC%9E%90%EB%B0%94%EC%9D%98%EC%8B%A0/JAVA%EC%9D%98%20%ED%8A%B9%EC%A7%95%20%EB%B0%8F%20%EC%9E%90%EB%B0%94%20%EC%BD%94%EB%93%9C%EB%8A%94%20%EC%96%B4%EB%96%BB%EA%B2%8C%20%EC%8B%A4%ED%96%89%EB%90%98%EB%8A%94%EA%B0%80.md#%EB%B0%94%EC%9D%B4%ED%8A%B8%EC%BD%94%EB%93%9C%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80"> 바이트코드란 무엇인가 </a>
- <a href="https://github.com/zlzzlzz2l/TIL_Today-I-Learn/blob/main/JAVA/%EC%9E%90%EB%B0%94%EC%9D%98%EC%8B%A0/JAVA%EC%9D%98%20%ED%8A%B9%EC%A7%95%20%EB%B0%8F%20%EC%9E%90%EB%B0%94%20%EC%BD%94%EB%93%9C%EB%8A%94%20%EC%96%B4%EB%96%BB%EA%B2%8C%20%EC%8B%A4%ED%96%89%EB%90%98%EB%8A%94%EA%B0%80.md#jit-%EC%BB%B4%ED%8C%8C%EC%9D%BC%EB%9F%AC%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B4%EB%A9%B0-%EC%96%B4%EB%96%BB%EA%B2%8C-%EB%8F%99%EC%9E%91%ED%95%98%EB%8A%94%EA%B0%80"> JIT 컴파일러란 무엇이며 어떻게 동작하는가 </a>
- <a href="https://github.com/zlzzlzz2l/TIL_Today-I-Learn/blob/main/JAVA/%EC%9E%90%EB%B0%94%EC%9D%98%EC%8B%A0/JAVA%EC%9D%98%20%ED%8A%B9%EC%A7%95%20%EB%B0%8F%20%EC%9E%90%EB%B0%94%20%EC%BD%94%EB%93%9C%EB%8A%94%20%EC%96%B4%EB%96%BB%EA%B2%8C%20%EC%8B%A4%ED%96%89%EB%90%98%EB%8A%94%EA%B0%80.md#jvm-%EA%B5%AC%EC%84%B1-%EC%9A%94%EC%86%8C"> JVM 구성 요소 </a>
- <a href="https://github.com/zlzzlzz2l/TIL_Today-I-Learn/blob/main/JAVA/%EC%9E%90%EB%B0%94%EC%9D%98%EC%8B%A0/JAVA%EC%9D%98%20%ED%8A%B9%EC%A7%95%20%EB%B0%8F%20%EC%9E%90%EB%B0%94%20%EC%BD%94%EB%93%9C%EB%8A%94%20%EC%96%B4%EB%96%BB%EA%B2%8C%20%EC%8B%A4%ED%96%89%EB%90%98%EB%8A%94%EA%B0%80.md#jdk%EC%99%80-jre%EC%9D%98-%EC%B0%A8%EC%9D%B4"> JDK와 JRE의 차이 </a>

---

## JVM이란 무엇인가?

### JVM이란?

- 바이트 코드를 실행시켜주는 주체
- 운영체제마다 독립적인 JVM을 가지고 있기 때문에 바이트 코드만 가지고 있다면 JVM이 해당 운영체제 환경에 맞춰 코드 실행

### JVM의 특징

- JVM을 두어 여러 운영체제에서 동일한 실행 결과가 나오고, 개발자는 운영체제와 상관없이 자바 프로그램을 개발 가능

- 바이트코드는 모든 JVM에서 같은 실행 결과를 보장하지만 JVM은 운영체제에 종속적이기 때문에 운영체제에 맞는 JVM을 설치해야 한다.

---

## 컴파일 하는 방법

![image](https://user-images.githubusercontent.com/48669011/135391987-c92b9c44-44c0-4404-86c9-338272b2993a.png)

1. .java 파일에 코드를 작성한다.
2. javac를 이용하여 .java 파일을 컴파일하면 .class 파일로 바이트 코드 생성

---

## 실행 방법

```java
   java classFileName.class
```

- 커멘트 라인에 명령어를 입력하면 Java Application이 실행되면서 JVM의 클래스 로더가 동적으로 바이트 코드를 로딩

---

## 바이트코드란 무엇인가

- JVM이 이해할 수 있는 언어
- JIT 컴파일러에 의해 바이너리 코드로 변환

### 바이너리 코드

- 컴퓨터가 이해할 수 있는 0과 1로 구성된 코드
- CPU가 이해할 수 있는 언어

---

## JIT 컴파일러란 무엇이며 어떻게 동작하는가

### JIT 컴파일러란?

: 프로그램을 실제 실행하는 시점에 기계어로 번역하는 컴파일러이다.

### JIT 컴파일러 동작방식

: 자바는 바이트코드로 컴파일 하는 과정 → 바이트코드를 인터프리터하는 방식을 거친다. 컴파일하면서 자주 사용되는 부분들은 기계어로 캐싱하고, 코드를 다시 컴파일할 때 모든 코드를 컴파일하는 게 아니라 바뀐 부분만 컴파일하고 나머지는 캐싱된 코드를 사용한다.

⇒ 이를 통해 인터프리터의 속도를 개선할 수 있다.

---

## JVM 구성 요소

![image](https://user-images.githubusercontent.com/48669011/135392117-5196ff77-c5d6-4e72-b877-62d961fe5ae6.png)

- Class Loader
- Runtime data area
- Execution engine

---

### Class Loader

- First main component
- .java 파일을 컴파일 한 후, 생성된 .class 파일을 Class Loader가 동적으로 메모리에 올린다.
- 클래스 로더는 3가지 양상을 가진다.

### **Loading**

- Bootstrap class loader
    - 런타임(RT).jar로부터 pre-compiled된 또는 pre-trusted한 .class를 로드
- Extension class loader
    - 추가적인 클래스 파일을 로드
    - ex) 오라클 DB를 이용한다면 OJDBC 패키지 필요한데, Extension class loader에 의해 메모리에 로드
- Application class loader
    - .class 파일로 컴파일 되면 JVM이 애플리케이션 클래스 로더에 의해서 메모리에 로드 되는데, 여기서 Application class loader가 .class 파일을 메모리에 로드

### **Linking**

- verify
    - 바이트 코드 클래스 파일이 표준을 준수하는지 확인하는 단계
- prepare
    - 정적(static) 변수 및 default value(int, boolean 등 지정 안된 기본값들)들이 메모리 공간에 할당
- resolve
    - Symbolic Reference들이 실제 참조들로 대체

### **Initialization**

- 모든 정적 변수가 실제 값들로 할당되며, 초기화 작업 이루어짐
- static initializers이 진행된다. (static block)

---

## Runtime Data Area

- second main component
- JVM이 바이트 코드를 실행하기 위해 사용하기 위한 메모리 공간

### **Method Area**

- 모든 클래스 레벨 데이터는 이 영역에 저장
- 클래스 로더가 클래스 파일을 읽어오면 클래스 정보를 파싱해서 이 곳에 저장
    - 변수 어떤거?
    - 메서드 어떤거?
    - 정적 변수 어떤거?
- 모든 스레드가 공유

### **Heap Area**

- 모든 Object와 인스턴스 변수 저장
- 모든 스레드가 공유

### **Stack Memory**

- 3개의 section으로 구성
    - Local Variable
        
        모듈 내에서 사용되는 모든 로컬 변수를 저장하는 영역
        
    - Operand stack
        
        메서드 내에서 사용되는 모든 피연산자 포함
        
    - Frame data
        
        메서드에서 예외가 발생할 경우 모든 캐치 블록 정보 포함해서 저장
        
- 스레드마다 존재
- 스레드 별로 1개만 존재하고, 스택 프레임은 메서드가 호출될 때마다 생성
- 메서드 실행이 끝나면 스택 프레임은 pop되어 스택에서 제거된다.

### **PC Register**

- 현재 실행 중인 명령을 가리킴
- 스레드마다 존재

### **Native Method Stack**

- 네이티브 메서드를 위한 스택
- 바이트 코드가 아닌 다른 언어로 작성된 메서드
- 자바 성능을 향상시키기 위한 목적으로 사용
- 스레드마다 존재

---

### Execution Engine

- 바이트 코드를 기계 코드로 변환하고 명령을 실행하는 영역

### Interpreter

- 클래스 파일이나 바이트 코드를 읽고 하나씩 실행하는 인터프리터
- 이것의 문제는 어떤 메서드가 여러 번 호출될 때, 그 바이트 코드의 행을 반복해서 해석한다는 것

### JIT Compiler

- 인터프리터의 문제를 해결하는데 도움
- 메서드 호출이 반복되면 바이트 코드를 네이티브 코드로 컴파일한다.
- 네이티브 코드는 반복 메서드 호출에 직접 사용된다.
- 위 기능을 수행하기 위해서 몇 가지 구성 요소를 포함
    - Intermediate code generator - 중간 코드 생성
    - Code Optimizer - 중간 코드를 최적화하여 성능 향상
    - Target code generator - 중간 코드를 기본 컴퓨터 코드로 변환
    - Profiler - 반복적으로 호출되는 핫스팟, 메서드를 찾는 역할

### Garbage Collector

- 더 이상 사용되지 않는 Object를 없애는 역할

### Java Native Method Interface

- 네이티브 라이브러리와 상호 작용을 담당하며 JVM이 사용할 수 있도록 한다.

---

## JDK와 JRE의 차이

- JDK(Java Development Kit, 자바 개발 키트)

  : 프로그램 개발에 필요한 JVM, 라이브러리 API, 컴파일러 등의 개발도구가 포함되어 있다.

  : `JRE` + `개발에 필요한 도구`

- JRE(Java Runtime Environment, 자바 실행 환경)

  : 프로그램 실행에 필요한 JVM, 라이브러리 API만 포함되어 있다.

  : `JVM` + `표준 클래스 라이브러리`

프로그램을 개발하고자 한다면 JDK를 설치하고, 이미 개발된 프로그램을 실행한다면 JRE만 설치하면 된다. 

하지만 JRE는 Java9부터 없어졌다. 왠만하면 JDK로 해결할 수 있다. JDK 안에 JRE도 들어있기 때문이다.
